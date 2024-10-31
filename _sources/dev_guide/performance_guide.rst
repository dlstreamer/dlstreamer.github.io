Performance Guide
=================

1. Media and AI processing (single stream)
------------------------------------------

The Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework combines media processing with AI inference capabilities. 
The simplest pipeline detects objects in a video stream stored as a disk file.

The following command line is recommended for Intel platforms with integrated GPU and/or NPU devices:

-  'vah264dec' element uses hardware video decoder to generate output images (VAMemory).
-  'gvadetect' element consumes VAMemory images (zero-copy operation) and generates inference results. 
-  'pre-process-backend=va' uses hardware image scaler to resize VAMemory image into input model tensor dimensions.

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va ! queue ! gvafpscounter ! fakesink
    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! gvadetect model=${MODEL_FILE} device=NPU pre-process-backend=va ! queue ! gvafpscounter ! fakesink

When using discrete GPUs it is recommended to set 'pre-process-backend=va-surface-sharing' to enforce zero-copy operation between video decoder and AI inference engine.

Please note 'va-surface-sharing' may be slightly slower than 'va' backend on platforms with integrated GPU device. 
The 'va-surface-sharing' option compiles the image scaling layer into the AI model, hence it consumes GPU compute resources.

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va-surface-sharing ! queue ! gvafpscounter ! fakesink

While GPU device is preferred for hardware-accelerated media decoding, it is also possible to decode video streams using CPU device.
The following table lists commands lines recommended pipelines for various combinations of media decode and AI inference devices.

.. list-table::
   :header-rows: 1

   * - Media Decode device
     - Inference device
     - Sample command line
   * - GPU
     - | GPU
       | *or*
       | NPU
     - gst-launch-1.0 filesrc location=${VIDEO_EXAMPLE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va ! queue ! gvafpscounter ! fakesink
   * - GPU
     - CPU
     - gst-launch-1.0 filesrc location=${VIDEO_EXAMPLE} ! parsebin ! vah264dec ! "video/x-raw" ! gvadetect model=${MODEL_FILE} device=CPU pre-process-backend=opencv ! queue ! gvafpscounter ! fakesink
   * - CPU
     - | GPU
       | *or*
       | NPU
     - gst-launch-1.0 filesrc location=${VIDEO_EXAMPLE} ! parsebin ! avdec_h264 ! "video/x-raw" ! gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=opencv ! queue ! gvafpscounter ! fakesink
   * - CPU
     - CPU
     - gst-launch-1.0 filesrc location=${VIDEO_EXAMPLE} ! parsebin ! avdec_h264 ! "video/x-raw" ! gvadetect model=${MODEL_FILE} device=CPU pre-process-backend=opencv ! queue ! gvafpscounter ! fakesink

2. Multi-stage pipeline with gvadetect and gvaclassify
------------------------------------------------------

The rules outlined above can be combined to create multi-stage pipelines. For example, the first two inference stages can use GPU and NPU devices with VA backend. 
The third element may use CPU device, after the video stream is copied from device memory (VAMemory) to system memory. 

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=GPU pre-process-backend=va ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=NPU pre-process-backend=va ! queue ! \
    vapostproc ! video/x-raw ! \
    gvaclassify model=${MODEL_FILE_3} device=CPU pre-process-backend=opencv ! queue ! \
    gvafpscounter ! fakesink

Please note 'queue' elements following each inference element (gvadetect and gvaclassify).
The inference elements process output tensors asynchronously in the context of OpenVINO™ threads. 
For performance reasons, the asynchronous calls should complete as soon as possible - hence 'queue' elements.

Static allocation of AI stages to inference devices may be suboptimal if one model is much bigger than others.
In such case, it is recommended to use 'virtual' aggregated devices and let the OpenVINO™ inference engine to select devices dynamically.
The pre-processing backend should be selected to handle all possible combinations.

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvaclassify model=${MODEL_FILE_3} device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvafpscounter ! fakesink

3. Multi-stream pipelines with single AI stage
----------------------------------------------

The GStreamer framework can execute multiple input streams in parallel. If streams use the same pipeline configuration, it is recommended to create a shared inference element.
The 'model-instance-id=inf0' parameter constructs such element. In addition, the 'batch-size' element should be set to the integer multiply of stream count.
This approach batches images from different streams to maximize throughput and at the same time reduce latency penalty due to batching. 

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE_1} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_2} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_3} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_4} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink

Similarly as for multi-stage scenarios, an aggregated inference device can be used with 'device=MULTI:GPU,NPU,CPU'.

Please note a single DL Streamer command line with multiple input streams yields higher performance than running multiple
DL Streamer command lines each processioning a single single stream. The reason is multiple command lines cannot benefit
from sharing one AI model instance and cross-stream batching.

4. Multi-stream pipelines with multiple AI stages
-------------------------------------------------

The multi-stage and multi-stream scenarios can be combined to form complex execution graphs.
In the following example four input streams are processed by gvadetect and gvaclassify.
Note the pipeline creates only two instances of inference models:

-  'inf1' with detection model running on GPU
-  'inf2' with classification model running on NPU

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE_1} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_2} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_3} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    filesrc location=${VIDEO_FILE_4} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE_1} device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=${MODEL_FILE_2} device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink

5. GPU device selection
-------------------------

The GStreamer framework allows selecting the GPU render device for VA codecs plugins if there is more than one GPU device on the system.

For a single GPU device system, the VA codecs plugin elements like vah264dec, vapostproc, etc., correspond to the GPU (GPU.0) device -> /dev/dri/renderD128.

For multi-GPU systems, each additional GPU device corresponds to a separate DRI device. e.g. 

-  GPU.1 -> /dev/dri/renderD129, 

-  GPU.2 -> /dev/dri/renderD130 etc.


The command below lists the available VA codecs plugins on the system for each GPU device

.. code:: shell

    gst-inspect-1.0 | grep va
    . . .
    va:  vah264dec: VA-API H.264 Decoder in Intel(R) Gen Graphics
    va:  vapostproc: VA-API Video Postprocessor in Intel(R) Gen Graphics
    . . .
    va:  varenderD129h264dec: VA-API H.264 Decoder in Intel(R) Gen Graphics in renderD129
    va:  varenderD129postproc: VA-API Video Postprocessor in Intel(R) Gen Graphics in renderD129
    . . .
    va:  varenderD130h265dec: VA-API H.265 Decoder in Intel(R) Gen Graphics in renderD130
    va:  varenderD130postproc: VA-API Video Postprocessor in Intel(R) Gen Graphics in renderD130



Example of **GPU.0** and coresponding VA codec elements, e.g. **vah264dec** and **vapostproc** usage:

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! vah264dec ! vapostproc ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU.0 pre-process-backend=va-surface-sharing batch_size=8 ! queue ! gvafpscounter ! fakesink



For GPU devices other than the default one(i.e. GPU or GPU.0) the renderD12 **X** component selects assigned GPU device e.g.: 

- **GPU.1** -> va **renderD129** h264dec, va **renderD129** postproc,

- **GPU.2** -> va **renderD130** h264dec, va **renderD130** postproc


Example of **GPU.1** and coresponding VA codec elements, e.g. **varenderD129h264dec** and **varenderD129postproc** usage.

.. code:: shell

    gst-launch-1.0 filesrc location=${VIDEO_FILE} ! parsebin ! varenderD129h264dec ! varenderD129postproc ! "video/x-raw(memory:VAMemory)" ! \
    gvadetect model=${MODEL_FILE} device=GPU.1 pre-process-backend=va-surface-sharing batch_size=8 ! queue ! gvafpscounter ! fakesink



6. Using GStreamer framework **compositor** element for merging many video displays into single view
--------------------------------------------------------------------------------------

The GStreamer framework `compositor <https://gstreamer.freedesktop.org/documentation/compositor/index.html?gi-language=c#compositor-page>`__ element allows to 
merge multiple displays into one.

Add **compositor** element along with its name e.g. **name=comp** and the sink pad x,y coordinates position e.g. **sink_0::xpos=0 sink_0::ypos=0** to GStreamer framework pipeline.
Each output display requires a separate sink pad definition. The last component is **autovideosink sync=false**.

.. code:: shell

   compositor name=comp sink_0::xpos=0 sink_0::ypos=0 sink_1::xpos=720 sink_1::ypos=0 ... ! autovideosink sync=false

The below example presents usage of the GStreamer framework **compositor** element for merging 4 output videos into a single display.

.. code:: shell

   gst-launch-1.0 compositor name=comp sink_0::xpos=0 sink_0::ypos=0 sink_1::xpos=720 sink_1::ypos=0 sink_2::xpos=0 sink_2::ypos=400 sink_3::xpos=720 sink_3::ypos=400 ! autovideosink sync=false \
   filesrc location=${VIDEO_FILE_1} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
   gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvawatermark ! videoconvert ! gvafpscounter ! comp.sink_0  \
   filesrc location=${VIDEO_FILE_2} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
   gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvawatermark ! videoconvert ! gvafpscounter ! comp.sink_1 \
   filesrc location=${VIDEO_FILE_3} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
   gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvawatermark ! videoconvert ! gvafpscounter ! comp.sink_2 \
   filesrc location=${VIDEO_FILE_4} ! parsebin ! vah264dec ! "video/x-raw(memory:VAMemory)" ! \
   gvadetect model=${MODEL_FILE} device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvawatermark ! videoconvert ! gvafpscounter ! comp.sink_3


.. image:: gstreamer_compositor_dls_4outputs.png


7. The Intel® DL Streamer Pipeline Framework performance benchmark results
--------------------------------------------------------------------------

The Intel® DL Streamer Pipeline Framework example performance benchmark results can be found as a part of the `Smart Cities Accelerated by Intel® Graphics Solutions paper <https://www.intel.com/content/www/us/en/secure/content-details/826398/smart-cities-accelerated-by-intel-gpus-arc-gpu-addendum.html?wapkw=smart%20cities&DocID=826398>`__.
