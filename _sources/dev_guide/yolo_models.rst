Yolo Models
===========

This page illustrates how to prepare models from the **YOLO** family for integration with the Intel® DL Streamer pipeline.

.. note::
   
   The instructions provided below are comprehensive, but for convenience, it is recommended to use the `download_public_models.sh <https://github.com/dlstreamer/dlstreamer/blob/master/samples/download_public_models.sh>`_ script. This script will download all supported Yolo models and perform the necessary conversions automatically.
   
   
1. Setup
--------

The instructions assume Intel® DL Streamer framework is installed on the local system along with Intel® OpenVINO™ model downloader and converter tools,
as described here: `Tutorial <https://dlstreamer.github.io/get_started/tutorial.html#tutorial-setup>`__.

For YoloV5, YoloV8, YoloV9 and YoloV10 models it is also necessary to install the Ultralytics Python package:

.. code:: sh

   pip install ultralytics

2. YoloV8, YoloV9, YoloV10
--------------------------

Python script converting the recent Ultralytics models to Intel® OpenVINO™ format (replace *MODEL_NAME* with "yolov8s.pt", "yolov9c.pt" or "yolov10s.pt"):

.. code-block:: python

   from ultralytics import YOLO
   model = YOLO(MODEL_NAME)
   model.info()
   model.export(format='openvino')

For model YoloV10 modify model_type as below:

.. code-block:: python

   from ultralytics import YOLO
   import openvino, sys, shutil
   model = YOLO(MODEL_NAME)
   model.info()
   converted_path = model.export(format='openvino')
   converted_model = converted_path + '/yolov10s.xml'
   core = openvino.Core()
   ov_model = core.read_model(model=converted_model)
   ov_model.set_rt_info("yolo_v10", ['model_info', 'model_type'])
   openvino.save_model(ov_model, './FP32/yolov10s.xml', compress_to_fp16=False)
   openvino.save_model(ov_model, './FP16/yolov10s.xml', compress_to_fp16=True)
   shutil.rmtree(converted_path)

3. YoloV7
---------

Model preparation:

.. code:: sh

   git clone https://github.com/WongKinYiu/yolov7.git
   cd yolov7
   python3 export.py --weights yolov7.pt --grid --dynamic-batch
   ovc yolov7.onnx

4. YoloV5 latest version
------------------------
Model preparation enabling the dynamic batch size:

.. code-block:: python

   from ultralytics import YOLO
   from openvino.runtime import Core
   from openvino.runtime import save_model
   model = YOLO("yolov5s.pt")
   model.info()
   model.export(format='openvino', dynamic=True)  # creates 'yolov5su_openvino_model/'
   core = Core()
   model = core.read_model("yolov5su_openvino_model/yolov5su.xml")
   model.reshape([-1, 3, 640, 640])
   save_model(model, "yolov5su.xml")

5. YoloV5 older versions
------------------------

Model preparation of YoloV5 7.0 from Ultralytics involves two steps.
First, convert the PyTorch model to Intel® OpenVINO™ format : 

.. code:: sh

    git clone https://github.com/ultralytics/yolov5
    cd yolov5
    wget https://github.com/ultralytics/yolov5/releases/download/v7.0/yolov5s.pt
    python3 export.py --weights yolov5s.pt --include openvino --dynamic

Then, reshape the model to enable the dynamic batch size and keep other dimensions fixed:

.. code-block:: python

   from openvino.runtime import Core
   from openvino.runtime import save_model
   core = Core()
   model = core.read_model("yolov5s_openvino_model/yolov5s.xml")
   model.reshape([-1, 3, 640, 640])
   save_model(model, "yolov5s.xml")

6. YoloX
--------

Intel® OpenVINO™ version of the model can be obtained from the ONNX file:

.. code:: sh

   wget https://github.com/Megvii-BaseDetection/YOLOX/releases/download/0.1.1rc0/yolox_s.onnx
   ovc yolox_s.onnx --compress_to_fp16=False



7. Model usage
--------------

See `Samples <https://github.com/dlstreamer/dlstreamer/tree/master/samples/gstreamer/gst_launch/detection_with_yolo>`__ 
for detailed examples of Intel® DL Streamer pipelines using different Yolo models.
