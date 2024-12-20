GPU device selection
====================

This page describes GPU device selection on a multi-GPU system.

1. Media (VAAPI based) elements
-------------------------------

GStreamer `VAAPI plugin <https://gstreamer.freedesktop.org/documentation/vaapi/index.html>`__ supports environment variable
**GST_VAAPI_DRM_DEVICE** which allows to select GPU device for VAAPI elements (and ``decodebin`` element in case it
internally works on VAAPI elements).

The environment variable **GST_VAAPI_DRM_DEVICE** expects GPU device driver path,
the path ``/dev/dri/renderD128`` typically represents first GPU device on system,
``/dev/dri/renderD129`` represents second GPU device on system, etc.

For example, the following command forces VAAPI elements (and decodebin) to use second GPU device

.. code-block:: none

    export GST_VAAPI_DRM_DEVICE=/dev/dri/renderD129

2. Inference (OpenVINO™ based) elements
---------------------------------------

Explicit selection
^^^^^^^^^^^^^^^^^^

In case of video decode running on CPU and inference running on GPU, the ``device`` property in inference elements allows
to select GPU device according to `OpenVINO™ GPU device naming <https://docs.openvino.ai/2024/openvino-workflow/running-inference/inference-devices-and-modes/gpu-device.html#device-naming-convention>`__
with devices enumerated as "GPU.0", "GPU.1", etc, for example:

.. code:: shell

    gst-launch-1.0 "... ! decodebin force-sw-decoders=true ! gvadetect device=GPU.1 ! ..."

Automatic selection
^^^^^^^^^^^^^^^^^^^

In case of both video decode and inference running on GPU, select GPU device via setting environment variable for VAAPI decode element,
and set ``device=GPU`` for all inference elements. It allows inference elements to query VAAPI context from VAAPI decode element
and automatically run inference and pre-processing on same GPU device as video decode (GPU device affinity).
For example (selecting second GPU device for decode and inference):

.. code:: shell

    export GST_VAAPI_DRM_DEVICE=/dev/dri/renderD129
    gst-launch-1.0 "... ! decodebin ! gvadetect device=GPU ! ..."
