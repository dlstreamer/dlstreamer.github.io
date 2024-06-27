Yolo Models Preparation
=======================

This page illustrates how to prepare models from the **YOLO** family for integration with the Intel® DL Streamer pipeline.

.. note::
   The steps outlined below enable the creation of basic model versions, ready for use in Intel® DL Streamer. However, for YoloV5 (both versions) and YoloV7, additional operations not covered here are required if the batch size is to exceed 1. 
   
   It is recommended to use the download_public_models.sh script, which automatically downloads all supported Yolo models and carries out a complete conversion, allowing for the utilization of their full potential.

1. Setup
--------

The instructions assume Intel® DL Streamer framework is installed on the local system along with Intel® OpenVINO™ model downloader and converter tools,
as described here: `Tutorial <https://dlstreamer.github.io/get_started/tutorial.html#tutorial-setup>`__.

For YoloV5, YoloV8 and YoloV9 models it is also necessary to install the Ultralytics python package:

.. code:: sh

   pip install ultralytics

2. YoloV5u, YoloV8, YoloV9
--------------------------

Python script converting the recent Ultralytics models to Intel® OpenVINO™ format (replace *MODEL_NAME* with yolov5su.pt, yolov8s.pt, yolov9c.pt etc.):

.. code-block:: python

   from ultralytics import YOLO
   model = YOLO(MODEL_NAME)
   model.info()
   model.export(format='openvino')  

3. YoloV7
---------

Model preparation:

.. code:: sh

   git clone https://github.com/WongKinYiu/yolov7.git
   cd yolov7
   python3 export.py --weights yolov7.pt --grid
   ovc yolov7.onnx

4. YoloV5 older versions
------------------------

Model preparation of YoloV5 7.0 from Ultralytics:

.. code:: sh

    git clone https://github.com/ultralytics/yolov5
    cd yolov5
    wget https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5s.pt
    python3 export.py --weights yolov5s.pt --include openvino

5. YoloX
--------

Intel® OpenVINO™ version of the model can be downloaded directly:

.. code:: sh

   wget https://github.com/Megvii-BaseDetection/YOLOX/releases/download/0.1.1rc0/yolox_s_openvino.tar.gz
   tar -xvf ./yolox_s_openvino.tar.gz



6. Model usage
--------------

See `Samples <https://github.com/dlstreamer/dlstreamer/tree/master/samples/gstreamer/gst_launch/detection_with_yolo>`__ 
for detailed examples of Intel® DL Streamer pipelines using different Yolo models.
