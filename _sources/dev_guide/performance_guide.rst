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

    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va ! queue ! gvafpscounter ! fakesink
    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! gvadetect model=<MODEL_FILE> device=NPU pre-process-backend=va ! queue ! gvafpscounter ! fakesink

When using discrete GPUs it is recommended to set 'pre-process-backend=va-surface-sharing' to enforce zero-copy operation between video decoder and AI inference engine.

Please note 'va-surface-sharing' may be slightly slower than 'va' backend on platforms with integrated GPU device. 
The 'va-surface-sharing' option compiles the image scaling layer into the AI model, hence it consumes GPU compute resources.

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va-surface-sharing ! queue ! gvafpscounter ! fakesink

The hardware-accelerated decoder is recommended even when using CPU device for inference. 
The decoded image should be stored in system (CPU) memory and handled with OpenCV preprocessor backend (pre-proc-backend=opencv).

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw ! gvadetect model=<MODEL_FILE> device=CPU pre-process-backend=opencv ! queue ! gvafpscounter ! fakesink


2. Multi-stage pipeline with gvadetect and gvaclassify
------------------------------------------------------

The rules outlined above can be combined to create multi-stage pipelines. For example, the first two inference stages can use GPU and NPU devices with VA backend. 
The third element may use CPU device, after the video stream is copied from device memory (VAMemory) to system memory. 

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=GPU pre-process-backend=va ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=NPU pre-process-backend=va ! queue ! \
    vapostproc ! video/x-raw ! \
    gvaclassify model=<MODEL_FILE_3> device=CPU pre-process-backend=opencv ! queue ! \
    gvafpscounter ! fakesink

Please note 'queue' elements following each inference element (gvadetect and gvaclassify).
The inference elements process output tensors asynchronously in the context of OpenVINO™ threads. 
For performance reasons, the asynchronous calls should complete as soon as posssible - hence 'queue' elements.

Static allocation of AI stages to inference devices may be suboptimal if one model is much bigger than others.
In such case, it is recommended to use 'virtual' aggregated devices and let the OpenVINO™ inference engine to select devices dynamically.
The pre-processing backend should be selected to handle all possible combinations.

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvaclassify model=<MODEL_FILE_3> device=MULTI:GPU,NPU,CPU pre-process-backend=va ! queue ! \
    gvafpscounter ! fakesink

3. Multi-stream pipelines with single AI stage
----------------------------------------------

The GStreamer framework can execute multiple input streams in parallel. If streams use the same pipeline configuration, it is recommended to create a shared inference element.
The 'model-instance-id=inf0' parameter constructs such element. In addition, the 'batch-size' element should be set to the integer multiply of stream count.
This appraoch batches images from different streams to maximize throughtput and at the same time reduce latency penalty due to batching. 

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE_1> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_2> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_3> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_4> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE> device=GPU pre-process-backend=va model-instance-id=inf0 batch-size=4 ! queue ! gvafpscounter ! fakesink

Similarily as for multi-stage scenarios, an aggregated inference device can be used with 'device=MULTI:GPU,NPU,CPU'.

Please note a single DL Streamer command line with multiple input streams yields higher performance than running multiple
DL Streamer command lines each processesing a single single stream. The reason is multiple command lines cannot benefit
from sharing one AI model instance and cross-stream batching.

4. Multi-stream pipelines with mulitple AI stages
-------------------------------------------------

The multi-stage and multi-stream scenarios can be combined to form complex execution graphs.
In the following example four input streams are processed by gvadetect and gvaclassify.
Note the pipeline creates only two instances of inference models:

-  'inf1' with detection model running on GPU
-  'inf2' with classification model running on NPU

.. code:: shell

    gst-launch-10 filesrc location=<VIDEO_FILE_1> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_2> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_3> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink \
    gst-launch-10 filesrc location=<VIDEO_FILE_4> ! parsebin ! vah264dec ! video/x-raw(memory:VAMemory) ! \
    gvadetect model=<MODEL_FILE_1> device=GPU pre-process-backend=va model-instance-id=inf1 batch-size=4 ! queue ! \
    gvaclassify model=<MODEL_FILE_2> device=NPU pre-process-backend=va model-instance-id=inf2 batch-size=4 ! queue ! gvafpscounter ! fakesink
