YOLO Models
===========

This page illustrates how to prepare models from the **YOLO** family for integration with the Intel® DL Streamer pipeline.

.. note::
   
   The instructions provided below are comprehensive, but for convenience, it is recommended to use the `download_public_models.sh <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/download_public_models.sh>`_ script. This script will download all supported Yolo models and perform the necessary conversions automatically.
   
   See :doc:`download_public_models <download_public_models>` for more information.


1. Setup
--------

The instructions assume Intel® DL Streamer framework is installed on the local system along with Intel® OpenVINO™ model downloader and converter tools,
as described here: `Tutorial <https://dlstreamer.github.io/get_started/tutorial.html#tutorial-setup>`__.

For YOLOv5, YOLOv8, YOLOv9, YOLOv10, YOLO11 models it is also necessary to install the Ultralytics Python package:

.. code:: sh

   pip install ultralytics

2. YOLOv8, YOLOv9, YOLOv10, YOLO11
----------------------------------

Python script converting the recent Ultralytics models to Intel® OpenVINO™ format (replace *model_name* and *model_type* with the relevant models and types values):

Example for YOLO11 model:

.. code-block:: python

   from ultralytics import YOLO
   import openvino, sys, shutil, os

   model_name = 'yolo11s'
   model_type = 'yolo_v11'
   weights = model_name + '.pt'
   model = YOLO(weights)
   model.info()
   
   converted_path = model.export(format='openvino')
   converted_model = converted_path + '/' + model_name + '.xml'
   
   core = openvino.Core()
   
   ov_model = core.read_model(model=converted_model)
   if model_type in ["YOLOv8-SEG", "yolo_v11_seg"]:
       ov_model.output(0).set_names({"boxes"})
       ov_model.output(1).set_names({"masks"})
   ov_model.set_rt_info(model_type, ['model_info', 'model_type'])
   
   openvino.save_model(ov_model, './FP32/' + model_name + '.xml', compress_to_fp16=False)
   openvino.save_model(ov_model, './FP16/' + model_name + '.xml', compress_to_fp16=True)
   
   shutil.rmtree(converted_path)
   os.remove(f"{model_name}.pt")

3. YOLOv7
---------

Model preparation:

.. code:: sh

   git clone https://github.com/WongKinYiu/yolov7.git
   cd yolov7
   python3 export.py --weights yolov7.pt --grid --dynamic-batch
   # Convert the model to OpenVINO format FP32 precision
   ovc yolov7.onnx --compress_to_fp16=False
   # Convert the model to OpenVINO format FP16 precision
   ovc yolov7.onnx

4. YOLOv5 latest version
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

5. YOLOv5 older versions
------------------------

Model preparation of YOLOv5 7.0 from Ultralytics involves two steps.
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

6. YOLOX
--------

Intel® OpenVINO™ version of the model can be obtained from the ONNX file:

.. code:: sh

   wget https://github.com/Megvii-BaseDetection/YOLOX/releases/download/0.1.1rc0/yolox_s.onnx
   ovc yolox_s.onnx --compress_to_fp16=False



7. Model usage
--------------

See `Samples <https://github.com/dlstreamer/dlstreamer/tree/master/samples/gstreamer/gst_launch/detection_with_yolo>`__ 
for detailed examples of Intel® DL Streamer pipelines using different Yolo models.
