Supported Models
================

This page contains the table of models supported by Intel® DL Streamer.
Each model has a link (under the model name) to the original documentation with download instructions.

Most models are from `OpenVINO™ Open Model Zoo <https://github.com/openvinotoolkit/open_model_zoo/>`__
but some of them come from other sources.


Models Table
----------------

.. list-table::
    :header-rows: 1

    * - #
      - Category
      - Model Name
      - GFLOPs
      - labels-file
      - model-proc
      - Demo app

    * - 1
      - Detection
      - `yolo-v5 <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v5.json>`__
      -
    * - 2
      - Detection
      - `yolo-v7 <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v7.json>`__
      -
    * - 3
      - Detection
      - `yolo-v8 <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      -
      - not required
      -
    * - 4
      - Detection
      - `yolo-v8-OBB <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      -
      - not required
      -
    * - 5
      - Detection
      - `yolo-v9 <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      -
      - not required
      -
    * - 6
      - Detection
      - `yolo-x <https://dlstreamer.github.io/dev_guide/yolo_model_preparation.html>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-x.json>`__
      -
    * - 7
      - Detection
      - `CenterFace <https://github.com/Star-Clouds/CenterFace/tree/master>`__
      - 
      -
      - not required
      -
    * - 8
      - Emotion Recognition
      - `enet_b0_8_va_mtl <https://github.com/av-savchenko/face-emotion-recognition/tree/main>`__
      - 
      -
      - not required
      -
    * - 9
      - Instance Segmentation
      - `mask_rcnn_inception_resnet_v2_atrous_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mask_rcnn_inception_resnet_v2_atrous_coco>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/tree/master/samples/gstreamer/model_proc/public/mask-rcnn.json>`__
      - `mask_rcnn_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/mask_rcnn_demo/cpp>`__
    * - 10
      - Instance Segmentation
      - `mask_rcnn_resnet50_atrous_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mask_rcnn_resnet50_atrous_coco>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/tree/master/samples/gstreamer/model_proc/public/mask-rcnn.json>`__
      - `mask_rcnn_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/mask_rcnn_demo/cpp>`__
    * - 11
      - Classification
      - `efficientnet-v2-b0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/efficientnet-v2-b0>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 12
      - Classification
      - `efficientnet-v2-s <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/efficientnet-v2-s>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 13
      - Detection
      - `GETI_Detection <https://geti.intel.com/>`__
      - 
      -
      - not required
      -
    * - 14
      - Detection
      - `GETI_Detection_Oriented <https://geti.intel.com/>`__
      - 
      -
      - not required
      -
    * - 15
      - Segmentation
      - `GETI_Instance_Segmentation <https://geti.intel.com/>`__
      - 
      -
      - not required
      -
    * - 16
      - Classification
      - `GETI_Classification_Single_Label <https://geti.intel.com/>`__
      - 
      -
      - not required
      -
    * - 17
      - Classification
      - `GETI_Classification_Multi_Label <https://geti.intel.com/>`__
      - 
      -
      - not required
      -
    * - 18
      - Sound Classification
      - `aclnet <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/aclnet>`__
      - 1.42
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/aclnet.json>`__
      - `sound_classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/sound_classification_demo/python>`__
    * - 19
      - Action Recognition
      - `action-recognition-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/action-recognition-0001>`__
      - 
      - `kinetics_400.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/kinetics_400.txt>`__
      -
      - `action_recognition_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/action_recognition_demo/python>`__
    * - 20
      - Object Attributes
      - `age-gender-recognition-retail-0013 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/age-gender-recognition-retail-0013>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/age-gender-recognition-retail-0013.json>`__
      - `interactive_face_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/interactive_face_detection_demo/cpp_gapi>`__
    * - 21
      - Classification
      - `anti-spoof-mn3 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/anti-spoof-mn3>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/anti-spoof-mn3.json>`__
      - `interactive_face_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/interactive_face_detection_demo/cpp_gapi>`__
    * - 22
      - Classification
      - `densenet-121-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/densenet-121-tf>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 23
      - Classification
      - `dla-34 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/dla-34>`__
      - 6.1368
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 24
      - Action Recognition
      - `driver-action-recognition-adas-0002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/driver-action-recognition-adas-0002>`__
      - 
      - `driver_actions.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/driver_actions.txt>`__
      -
      - `action_recognition_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/action_recognition_demo/python>`__
    * - 25
      - Detection
      - `efficientdet-d0-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/efficientdet-d0-tf>`__
      - 2.54
      - `coco_91cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 26
      - Detection
      - `efficientdet-d1-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/efficientdet-d1-tf>`__
      - 6.1
      - `coco_91cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 27
      - Classification
      - `efficientnet-b0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/efficientnet-b0>`__
      - 0.819
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 28
      - Classification
      - `efficientnet-b0-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/efficientnet-b0-pytorch>`__
      - 0.819
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 29
      - Object Attributes
      - `emotions-recognition-retail-0003 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/emotions-recognition-retail-0003>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/emotions-recognition-retail-0003.json>`__
      - `interactive_face_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/interactive_face_detection_demo/cpp_gapi>`__
    * - 30
      - Detection
      - `face-detection-0200 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-0200>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-0200.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 31
      - Detection
      - `face-detection-0202 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-0202>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-0202.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 32
      - Detection
      - `face-detection-0204 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-0204>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-0204.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 33
      - Detection
      - `face-detection-0205 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-0205>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-0205.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 34
      - Detection
      - `face-detection-0206 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-0206>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-0206.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 35
      - Detection
      - `face-detection-adas-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-adas-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-adas-0001.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 36
      - Detection
      - `face-detection-retail-0004 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-retail-0004>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-retail-0004.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 37
      - Detection
      - `face-detection-retail-0005 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/face-detection-retail-0005>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/face-detection-retail-0005.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 38
      - Object Attributes
      - `facial-landmarks-35-adas-0002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/facial-landmarks-35-adas-0002>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/facial-landmarks-35-adas-0002.json>`__
      - `gaze_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/gaze_estimation_demo/cpp_gapi>`__
    * - 39
      - Object Attributes
      - `facial-landmarks-98-detection-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/facial-landmarks-98-detection-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/facial-landmarks-98-detection-0001.json>`__
      - `gaze_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/gaze_estimation_demo/cpp>`__
    * - 40
      - Detection
      - `faster_rcnn_inception_resnet_v2_atrous_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/faster_rcnn_inception_resnet_v2_atrous_coco>`__
      - 
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-image-info.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 41
      - Detection
      - `faster_rcnn_resnet50_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/faster_rcnn_resnet50_coco>`__
      - 
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-image-info.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 42
      - Classification
      - `googlenet-v1-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/googlenet-v1-tf>`__
      - 3.016
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 43
      - Classification
      - `googlenet-v2-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/googlenet-v2-tf>`__
      - 4.058
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 44
      - Classification
      - `googlenet-v3 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/googlenet-v3>`__
      - 11.469
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 45
      - Classification
      - `googlenet-v3-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/googlenet-v3-pytorch>`__
      - 11.469
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 46
      - Classification
      - `googlenet-v4-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/googlenet-v4-tf>`__
      - 24.584
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 47
      - Classification
      - `hbonet-0.25 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/hbonet-0.25>`__
      - 0.037
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 48
      - Classification
      - `hbonet-1.0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/hbonet-1.0>`__
      - 0.305
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 49
      - Head Pose Estimation
      - `head-pose-estimation-adas-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/head-pose-estimation-adas-0001>`__
      - 
      -
      -
      - `gaze_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/gaze_estimation_demo/cpp_gapi>`__
    * - 50
      - Detection
      - `horizontal-text-detection-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/horizontal-text-detection-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/horizontal-text-detection-0001.json>`__
      - `text_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/text_detection_demo/cpp>`__
    * - 51
      - Human Pose Estimation
      - `human-pose-estimation-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/human-pose-estimation-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/human-pose-estimation-0001.json>`__
      - `multi_channel_human_pose_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/multi_channel_human_pose_estimation_demo/cpp>`__
    * - 52
      - Classification
      - `inception-resnet-v2-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/inception-resnet-v2-tf>`__
      - 
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 53
      - Instance Segmentation
      - `instance-segmentation-person-0007 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-person-0007>`__
      - 
      -
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 54
      - Instance Segmentation
      - `instance-segmentation-security-0002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-security-0002>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 55
      - Instance Segmentation
      - `instance-segmentation-security-0091 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-security-0091>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 56
      - Instance Segmentation
      - `instance-segmentation-security-0228 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-security-0228>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 57
      - Instance Segmentation
      - `instance-segmentation-security-1039 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-security-1039>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 58
      - Instance Segmentation
      - `instance-segmentation-security-1040 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/instance-segmentation-security-1040>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `background_subtraction_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/background_subtraction_demo/cpp_gapi>`__
    * - 59
      - Object Attributes
      - `landmarks-regression-retail-0009 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/landmarks-regression-retail-0009>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/landmarks-regression-retail-0009.json>`__
      - `face_recognition_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/face_recognition_demo/python>`__
    * - 60
      - Optical Character Recognition
      - `license-plate-recognition-barrier-0007 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/license-plate-recognition-barrier-0007>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/license-plate-recognition-barrier-0007.json>`__
      - `security_barrier_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/security_barrier_camera_demo/cpp>`__
    * - 61
      - Classification
      - `mixnet-l <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mixnet-l>`__
      - 0.565
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 62
      - Classification
      - `mobilenet-v1-0.25-128 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v1-0.25-128>`__
      - 
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 63
      - Classification
      - `mobilenet-v1-1.0-224-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v1-1.0-224-tf>`__
      - 
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 64
      - Classification
      - `mobilenet-v2-1.0-224 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v2-1.0-224>`__
      - 
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 65
      - Classification
      - `mobilenet-v2-1.4-224 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v2-1.4-224>`__
      - 
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 66
      - Classification
      - `mobilenet-v2-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v2-pytorch>`__
      - 0.615
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 67
      - Classification
      - `mobilenet-v3-large-1.0-224-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v3-large-1.0-224-tf>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 68
      - Classification
      - `mobilenet-v3-small-1.0-224-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-v3-small-1.0-224-tf>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 69
      - Detection
      - `mobilenet-yolo-v4-syg <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/mobilenet-yolo-v4-syg>`__
      - 65.984
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/mobilenet-yolo-v4-syg.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 70
      - Classification
      - `nfnet-f0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/nfnet-f0>`__
      - 24.8053
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 71
      - Classification
      - `open-closed-eye-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/open-closed-eye-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/open-closed-eye-0001.json>`__
      - `gaze_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/gaze_estimation_demo/cpp_gapi>`__
    * - 72
      - Detection
      - `pedestrian-and-vehicle-detector-adas-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/pedestrian-and-vehicle-detector-adas-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/pedestrian-and-vehicle-detector-adas-0001.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 73
      - Detection
      - `pedestrian-detection-adas-0002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/pedestrian-detection-adas-0002>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/pedestrian-detection-adas-0002.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 74
      - Object Attributes
      - `person-attributes-recognition-crossroad-0230 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-attributes-recognition-crossroad-0230>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-attributes-recognition-crossroad-0230.json>`__
      - `crossroad_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/crossroad_camera_demo/cpp>`__
    * - 75
      - Object Attributes
      - `person-attributes-recognition-crossroad-0234 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-attributes-recognition-crossroad-0234>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-attributes-recognition-crossroad-0234.json>`__
      - `crossroad_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/crossroad_camera_demo/cpp>`__
    * - 76
      - Object Attributes
      - `person-attributes-recognition-crossroad-0238 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-attributes-recognition-crossroad-0238>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-attributes-recognition-crossroad-0238.json>`__
      - `crossroad_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/crossroad_camera_demo/cpp>`__
    * - 77
      - Detection
      - `person-detection-0200 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-0200>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-0200.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 78
      - Detection
      - `person-detection-0201 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-0201>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-0201.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 79
      - Detection
      - `person-detection-0202 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-0202>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-0202.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 80
      - Detection
      - `person-detection-0203 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-0203>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-0203.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 81
      - Detection
      - `person-detection-asl-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-asl-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-0203.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 82
      - Detection
      - `person-detection-retail-0013 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-detection-retail-0013>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-detection-retail-0013.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 83
      - Detection
      - `person-vehicle-bike-detection-2000 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-2000>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-2000.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 84
      - Detection
      - `person-vehicle-bike-detection-2001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-2001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-2001.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 85
      - Detection
      - `person-vehicle-bike-detection-2002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-2002>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-2002.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 86
      - Detection
      - `person-vehicle-bike-detection-2003 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-2003>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-2003.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 87
      - Detection
      - `person-vehicle-bike-detection-2004 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-2004>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-2004.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 88
      - Detection
      - `person-vehicle-bike-detection-crossroad-0078 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-crossroad-0078>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-crossroad-0078.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 89
      - Detection
      - `person-vehicle-bike-detection-crossroad-1016 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-crossroad-1016>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-crossroad-1016.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 90
      - Detection
      - `person-vehicle-bike-detection-crossroad-yolov3-1020 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/person-vehicle-bike-detection-crossroad-yolov3-1020>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/person-vehicle-bike-detection-crossroad-yolov3-1020.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 91
      - Detection
      - `product-detection-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/product-detection-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/product-detection-0001.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 92
      - Classification
      - `regnetx-3.2gf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/regnetx-3.2gf>`__
      - 6.3893
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 93
      - Classification
      - `repvgg-a0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/repvgg-a0>`__
      - 2.7286
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 94
      - Classification
      - `repvgg-b1 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/repvgg-b1>`__
      - 23.6472
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 95
      - Classification
      - `repvgg-b3 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/repvgg-b3>`__
      - 52.4407
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 96
      - Classification
      - `resnest-50-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/resnest-50-pytorch>`__
      - 10.8148
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 97
      - Classification
      - `resnet-18-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/resnet-18-pytorch>`__
      - 3.637
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 98
      - Classification
      - `resnet-34-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/resnet-34-pytorch>`__
      - 7.3409
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 99
      - Classification
      - `resnet-50-pytorch <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/resnet-50-pytorch>`__
      - 8.216
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 100
      - Classification
      - `resnet-50-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/resnet-50-tf>`__
      - 8.2164
      - `imagenet_2012_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 101
      - Classification
      - `resnet18-xnor-binary-onnx-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/resnet18-xnor-binary-onnx-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/resnet18-xnor-binary-onnx-0001.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 102
      - Classification
      - `resnet50-binary-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/resnet50-binary-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/resnet50-binary-0001.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 103
      - Detection
      - `retinanet-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/retinanet-tf>`__
      - 
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 104
      - Classification
      - `rexnet-v1-x1.0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/rexnet-v1-x1.0>`__
      - 0.8325
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 105
      - Detection
      - `rfcn-resnet101-coco-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/rfcn-resnet101-coco-tf>`__
      - 
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-image-info.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 106
      - Classification
      - `shufflenet-v2-x1.0 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/shufflenet-v2-x1.0>`__
      - 0.2957
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 107
      - Human Pose Estimation
      - `single-human-pose-estimation-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/single-human-pose-estimation-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/single-human-pose-estimation-0001.json>`__
      - `single_human_pose_estimation_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/single_human_pose_estimation_demo/python>`__
    * - 108
      - Detection
      - `ssd_mobilenet_v1_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/ssd_mobilenet_v1_coco>`__
      - 2.494
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 109
      - Detection
      - `ssd_mobilenet_v1_fpn_coco <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/ssd_mobilenet_v1_fpn_coco>`__
      - 123.309
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 110
      - Detection
      - `ssdlite_mobilenet_v2 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/ssdlite_mobilenet_v2>`__
      - 1.525
      - `coco_91cl_bkgr.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_91cl_bkgr.txt>`__
      -
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 111
      - Classification
      - `swin-tiny-patch4-window7-224 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/swin-tiny-patch4-window7-224>`__
      - 
      - `imagenet_2012.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/imagenet_2012.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/preproc-aspect-ratio.json>`__
      - `classification_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/classification_demo/python>`__
    * - 112
      - Object Attributes
      - `vehicle-attributes-recognition-barrier-0039 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-attributes-recognition-barrier-0039>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-attributes-recognition-barrier-0039.json>`__
      - `security_barrier_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/security_barrier_camera_demo/cpp>`__
    * - 113
      - Object Attributes
      - `vehicle-attributes-recognition-barrier-0042 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-attributes-recognition-barrier-0042>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-attributes-recognition-barrier-0042.json>`__
      - `security_barrier_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/security_barrier_camera_demo/cpp>`__
    * - 114
      - Detection
      - `vehicle-detection-0200 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-detection-0200>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-detection-0200.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 115
      - Detection
      - `vehicle-detection-0201 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-detection-0201>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-detection-0201.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 116
      - Detection
      - `vehicle-detection-0202 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-detection-0202>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-detection-0202.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 117
      - Detection
      - `vehicle-detection-adas-0002 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-detection-adas-0002>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-detection-adas-0002.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 118
      - Detection
      - `vehicle-license-plate-detection-barrier-0106 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/vehicle-license-plate-detection-barrier-0106>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/vehicle-license-plate-detection-barrier-0106.json>`__
      - `security_barrier_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/security_barrier_camera_demo/cpp>`__
    * - 119
      - Detection
      - `vehicle-license-plate-detection-barrier-0123 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/vehicle-license-plate-detection-barrier-0123>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/vehicle-license-plate-detection-barrier-0123.json>`__
      - `security_barrier_camera_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/security_barrier_camera_demo/cpp>`__
    * - 120
      - Action Recognition
      - `weld-porosity-detection-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/intel/weld-porosity-detection-0001>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/intel/weld-porosity-detection-0001.json>`__
      - `action_recognition_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/action_recognition_demo/python>`__
    * - 121
      - Detection
      - `yolo-v3-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/yolo-v3-tf>`__
      - 65.984
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v3-tf.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 122
      - Detection
      - `yolo-v3-tiny-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/yolo-v3-tiny-tf>`__
      - 5.582
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v3-tiny-tf.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 123
      - Detection
      - `yolo-v4-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/yolo-v4-tf>`__
      - 129.5567
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v4-tf.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 124
      - Detection
      - `yolo-v4-tiny-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master//models/public/yolo-v4-tiny-tf>`__
      - 6.9289
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/public/yolo-v4-tiny-tf.json>`__
      - `object_detection_demo <https://github.com/openvinotoolkit/open_model_zoo/tree/master//demos/object_detection_demo/cpp>`__
    * - 125
      - Classification
      - `mobilenetv2-7 <https://github.com/onnx/models/tree/main/validated/vision/classification/mobilenet>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/onnx/mobilenetv2-7.json>`__
      -
    * - 126
      - Classification
      - `emotion-ferplus-8 <https://github.com/onnx/models/tree/main/validated/vision/body_analysis/emotion_ferplus>`__
      - 
      -
      - `model-proc <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/model_proc/onnx/emotion-ferplus-8.json>`__
      -
    * - 127
      - Detection
      - `torchvision.models.detection. ssdlite320_mobilenet_v3_large <https://pytorch.org/vision/main/models/generated/torchvision.models.detection.ssdlite320_mobilenet_v3_large.html>`__
      - 0.583
      - `coco_80cl.txt <https://github.com/dlstreamer/dlstreamer/blob/master/samples/labels/coco_80cl.txt>`__
      -
      -

Legal Information
-------------------
PyTorch, TensorFlow, Caffe, Keras, MXNet are trademarks or brand names of their respective owners.
All company, product and service names used in this website are for identification purposes only.
Use of these names,trademarks and brands does not imply endorsement.
