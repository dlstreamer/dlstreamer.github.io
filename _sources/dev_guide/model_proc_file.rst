Model-proc File (legacy)
========================

.. warning::  
  The functionality described here has been **deprecated**. Avoid using it to prevent dealing with a legacy solution. It will be maintained for some time to ensure backwards compatibility, but you should not use it in modern applications.
  The new method of model preparation is described in `Model Info Section <https://dlstreamer.github.io/dev_guide/model_info_xml.html>`__

Contents
--------

-  :ref:`Overview <overview>`
-  :ref:`Pre-processing description input_preproc <input-preproc>`

   -  :ref:`Pre-processing configuration <input-preproc-configuration>`
   -  :ref:`Example <input-preproc-example>`

-  :ref:`Post-processing description output_postproc <output-postproc>`

   -  :ref:`Post-processing configuration <output-postproc-configuration>`
   -  :ref:`Example <output-postproc-example>`

.. _overview:

Overview
--------

A model-proc file is a regular JSON file with pre- and post-processing
configuration.

As an example implementation, see the model-proc file for the emotions
recognition model shown in the code snippet below.

``input_preproc`` set to ``[]`` indicates that images do not need to be
pre-processed with custom means before inference. They will be resized
without aspect-ratio preservation and their color space will be changed
to BGR.

``output_postproc`` says that the inference result is one of the strings
listed in ``"labels"``.

See the `samples/gstreamer/model_proc <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc>`__
for examples of .json files using various models from `Open Model Zoo <https://github.com/openvinotoolkit/open_model_zoo>`__ and some
public models.

.. code:: javascript

   {
       "json_schema_version": "2.2.0",
       "input_preproc": [],
       "output_postproc": [
         {
           "attribute_name": "emotion",
           "converter": "label",
           "method": "max",
           "labels": [
             "neutral",
             "happy",
             "sad",
             "surprise",
             "anger"
           ]
         }
       ]
   }

This file has specific fields:

* ``json_schema_version``. Service information needed by Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework. **The latest version should be used: 2.2.0**. 
* ``input_preproc``. Describes how to process an input tensor before inference. 
* ``output_postproc``. Describes how to process inference results.

.. _input-preproc:

Pre-processing description (``input_preproc``)
----------------------------------------------

.. _input-preproc-configuration:

Pre-processing configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Pre-processing is described by the ``input_preproc`` key.
``input_preproc`` value should contain an array of JSON objects with
pre-processing configuration. Each object describes operations for one
input layer. This array can be empty for models with one input layer. In
that case, tensors will be processed with default tensor pre-processing
(e.g., in case of image input: resize without aspect-ratio preservation
and color space conversion to BGR). Input pre-processing configuration
should be described in a key-value format. Valid keys for
``input_preproc`` are presented in the table below.


.. list-table::
   :header-rows: 1
   
   * - Key
     - 
     - Possible values or example
     - Description
     - Supported by backend
   * - layer_name
     - 
     - string
     - Neural network's input layer name.
     - All
   * - format
     -
     - | image,
       | image_info,
       | sequence_index
     - Input format for the layer with the specified name. In other words: "What to pre-process?". Can be one of the following:       
       
       * *image* - pre-process images;
       * *image_info* - pre-process additional layer with image info;
       * *sequence_index* - additional layer which is filled with ones
     - All
   * - params
     - resize
     - | no,
       | no-aspect-ratio,
       | aspect-ratio
     - Resize an image to match input model layer dimensions.
     - | opencv,
       | va,
       | va-surface-sharing
   * - params
     - crop
     - | central,
       | top_left,
       | top_right,
       | bottom_left,
       | bottom_right
     - Crop image to fit input model layer dimensions.
     - | opencv,
       | va,
       | va-surface-sharing
   * - params
     - color_space
     - | RGB,
       | BGR,
       | GRAYSCALE
     - Convert image to targeted color space.
     - | opencv, 
       | va,
       | va-surface-sharing (BGR only)
   * - params
     - range
     - [ 0.0, 1.0 ]
     - Normalize input image values to be in the specified range.
     - | opencv,
       | va-surface-sharing
       | ie
   * - params
     - mean
     - [ 0.485, 0.456, 0.406 ]
     - JSON arrays of doubles. Size of arrays should be equal to the number of channels of the input image.
     - | opencv,
       | va
   * - params
     - std
     - [ 0.229, 0.224, 0.225 ]
     - JSON arrays of doubles. Size of arrays should be equal to the number of channels of the input image.
     - | opencv,
       | va
   * - params
     - padding
     - | {
       |   "stride_x": 8,
       |   "stride_y": 8
       | }
     - A JSON object with stride in pixels from image boundaries (also can be set with *stride_x* and *stride_y*)
     - | opencv,
       | va,
       | va-surface-sharing


.. note:: 
  These operations will be performed in the order listed above,
  regardless of how they are listed in the model-proc file.
  If any operation is not specified, it will not be performed.

.. note::
  For the best performance normalize and color convert operation
  (BGR ⇒ RGB) it is worth excluding and adding the corresponding
  layers in the IR model using the appropriate model optimizer parameters.

.. _input-preproc-example:

Example
^^^^^^^

Example of what ``input_preproc`` and its parameters can look like are
in the code snippet below.

.. code:: javascript

   ...
   "input_preproc": [
       {
           "layer_name": "seq_ind",
           "format": "sequence_index"
       },
       {
           "format": "image_info",
           "layer_name": "image_info",
           "params": {
               "scale": 1.0
           }
       },
       {
           "layer_name": "input",
           "precision": "FP32",
           "format": "image",
           "params": {
               "resize": "aspect-ratio",
               "color_space": "BGR",
               "range": [ 0.0, 1.0 ],
               "mean": [ 0.485, 0.456, 0.406 ],
               "std": [ 0.229, 0.224, 0.225 ],
               "padding": {
                   "stride_x": 8,
                   "stride_y": 8
               }
           }
       }
   ], ...

.. _output-postproc:

Post-processing description (``output_postproc``)
-------------------------------------------------

.. _output-postproc-configuration:

Post-processing configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Post-processing is described in the similar to pre-processing fashion by
the ``output_postproc`` key. The key should contain an array of JSON
objects with post-processing configuration. Each object describes
operations for one output layer. This array can be empty for models with
one output layer. In that case, Pipeline Framework will detect the name of the
output layer and set a default converter for specified Pipeline Framework
inference element.

Pipeline Framework uses converters to transform output blob into suitable form.
Currently several converters are supported and its usage depends on what
model was used (whether detection, classification, or any other model).

Some converters may require the name of the output layer (usually applicable with ``gvaclassify``).
This can be done with the following fields:

* ``layer_name`` or ``layer_names`` - define for which layers transformation is applicable. Should be defined exactly one of them.
* ``attribute_name`` - name of output tensor for post-processing result.

**Default behavior**: Default output transformation method depends on
the used element. If described by the table behavior is suitable,
model-proc can be ignored.

.. list-table::
   :header-rows: 1

   * - Element
     - Default converter
   * - gvaclassify
     - raw_data_copy
   * - gvadetect
     - detection_output and boxes_labels (depends on model’s output)
   * - gvainference
     - raw_data_copy

The table below contains currently supported converters. Values in
*Converter* column contain a link to a model-proc file with this
converter. The last column contains a link to a model for which this
converter can be applied.

.. list-table::
   :header-rows: 1
   
   * - Converter
     - Description
     - Applied to output layer like
   * - **For gvainference**:
     -
     -
   * - raw_data_copy
     - Attach tensor data from all output layers in raw binary format and optionally tag the data format.
     - Basically any inference model
   * - **For gvadetect**:
     -
     -
   * - `detection_output <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/intel/face-detection-retail-0004.json>`__
     - Parse output blob produced by object detection neural network with *DetectionOutput* IR output layer's type. Output is RegionOfInterest.
       
       *labels* - an array of strings representing labels or a path to a file with labels where each label is on a new line.
     - `ssdlite_mobilenet_v2 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/ssdlite_mobilenet_v2#output>`__
     
       `person-vehicle-bike-detection-crossroad-0078 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/person-vehicle-bike-detection-crossroad-0078#outputs>`__
   * - `boxes_labels <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/intel/face-detection-0205.json>`__
     - Parse output blob produced by object detection neural network with two output layers: *boxes* and *labels*. Output is RegionOfInterest.
       
       *labels* - an array of strings representing labels or a path to a file with labels where each label is on a new line.
     - `face-detection-0205 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/face-detection-0205#outputs>`__
     
       `person-vehicle-bike-detection-2004 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/person-vehicle-bike-detection-2004#outputs>`__
   * - `yolo_v2 <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/public/yolo-v2-tf.json>`__
     - Parse output blob produced by object detection neural network with YOLO v2 architecture. Output is RegionOfInterest.
     
       * *labels* - an array of strings representing labels or a path to a file with labels where each label is on a new line;
       * *classes* - an integer number of classes;
       * *bbox_number_on_cell* - box count that can be predicted in each cell;
       * *anchors* - box size (x, y) is multiplied by this value. *len(anchors) == bbox_number_on_cell * 2 * number_of_outputs*;
       * *cells_number* - an image is split on cells with this number (if model's input layer has non-square form set *cells_number_x* & *cells_number_y* instead *cells_number*);
       * *iou_threshold* - parameter for NMS.
     - `yolo-v2-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/yolo-v2-tf#output>`__
     
       `yolo-v2-tiny-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/yolo-v2-tiny-tf#output>`__
   * - `yolo_v3 <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/public/yolo-v3-tf.json>`__
     - Parse output blob produced by object detection neural network with YOLO v3 architecture.
       
       * *labels* - an array of strings representing labels or a path to a file with labels where each label is on a new line;
       * *classes* - an integer number of classes;
       * *bbox_number_on_cell* - box count that can be predicted in each cell;
       * *anchors* - box size (x, y) is multiplied by this value. *len(anchors) == bbox_number_on_cell * 2 * number_of_outputs*;
       * *cells_number* - an image is split on cells with this number (if model's input layer has non-square form set *cells_number_x* & *cells_number_y* instead *cells_number*);
       * *iou_threshold* - parameter for NMS;
       * *masks*- determines what anchors are related to what output layer;
       * *output_sigmoid_activation* - performs sigmoid operation for coordinates and confidence.
       
       See more details :ref:`there <Build-model-proc-for-detection-model-with-advance-post-processing>`.
     - `yolo-v3-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/yolo-v3-tf#output>`__
     
       `yolo-v4-tf <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/yolo-v4-tf#output>`__
   * - heatmap_boxes
     - Parse output blob produced by network with DBNet architecture which is in the form of a probability heatmap. Output is RegionOfInterest.

       * *minimum_side* - Any detected box with its smallest side < minimum_side will be dropped;
       * *binarize_threshold* - Threshold value for OpenCV binary image thresholding, expected in range [0.0, 255.0];
     -
   * - **For gvaclassify**:
     -
     -
   * - `text <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/intel/age-gender-recognition-retail-0013.json>`__
     - Transform output tensor to text.
     
       * *text_scale* - scales data by this number;
       * *text_precision* - sets precision for textual representation.
     - `age-gender-recognition-retail-0013 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/age-gender-recognition-retail-0013#outputs>`__
   * - `label <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/intel/vehicle-attributes-recognition-barrier-0039.json>`__
     - Put an appropriate label for result.
       
       * *method*: one of [*max*, *index*, *compound* (threshold is required. 0.5 is default)];
       * *labels* - an array of strings representing labels or a path to a file with labels where each label is on a new line.
     - `emotions-recognition-retail-0003 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/age-gender-recognition-retail-0013#outputs>`__
     
       `license-plate-recognition-barrier-0007 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/license-plate-recognition-barrier-0001#outputs>`__
       
       `person-attributes-recognition-crossroad-0230 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/person-attributes-recognition-crossroad-0230#outputs>`__
   * - `keypoints_hrnet <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/public/single-human-pose-estimation-0001.json>`__
     - Parse output blob produced by network with HRNet architecture. Output tensor will have an array of key points.
       
       * *point_names* - an array of strings with the name of the points;
       * *point_connections* - an array of strings with points connection. The length should be even.
     - `single-human-pose-estimation-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/public/single-human-pose-estimation-0001#outputs>`__
   * - `keypoints_openpose <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/intel/human-pose-estimation-0001.json>`__
     - Parse output blob produced by network with OpenPose architecture. Output tensor will have an array of key points.
       
       * *point_names* - an array of strings with the name of the points;
       * *point_connections* - an array of strings with points connection. The length should be even.
     - `human-pose-estimation-0001 <https://github.com/openvinotoolkit/open_model_zoo/tree/master/models/intel/human-pose-estimation-0001#outputs>`__
   * - keypoints_3d
     - Parse output blob produced by network with HRNet architecture. Output tensor will have an array of 3D-key points.
       
       * *point_names* - an array of strings with the name of the points;
       * *point_connections* - an array of strings with points connection. The length should be even.
     - None
   * - **For gvaaudiodetect**:
     -
     -
   * - `audio_labels <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/gstreamer/model_proc/public/aclnet.json>`__
     - Output tensor - audio detections tensor.
       
       * *layer_name* - name of the layer to process;
       * *labels* - an array of JSON objects with index, label, threshold fields.
     - `aclnet <https://github.com/openvinotoolkit/open_model_zoo/blob/master/models/public/aclnet/README.md#output>`__



.. _output-postproc-example:

Example
^^^^^^^

See an example of what ``output_postproc`` and its parameters can look in the code snippet below.

.. note::
  This configuration cannot be used for any model.

.. code:: javascript

   ...
   "output_postproc": [
      {
          "converter": "raw_data_copy"
      },
      {
          "converter": "detection_output",
          "labels": [
              "background", "face"
          ]
      },
      {
          "converter": "yolo_v2",
          "classes": 20,
          "do_cls_softmax": true,
          "output_sigmoid_activation": true,
          "anchors": [
              1.08, 1.19, 3.42, 4.41, 6.63, 11.38, 9.42, 5.11, 16.62, 10.52
          ],
          "iou_threshold": 0.5,
          "bbox_number_on_cell": 5,
          "cells_number": 13,
          "labels": [
              "aeroplane", "bicycle", "bird", "boat", "bottle", "bus", "car",
              ...
              "pottedplant", "sheep", "sofa", "train", "tvmonitor"
          ]
      },
      {
          "converter": "text",
          "text_scale": 100.0,
          "text_precision": 0
          "layer_name": "age_conv3",
          "attribute_name": "age",
      },
      {
          "converter": "label",
          "labels": [
              "Female", "Male"
          ],
          "method": "max"
          "layer_name": "prob",
          "attribute_name": "gender",
      },
      {
          "converter": "label",
          "labels": "/opt/data/color_labels.txt",
          "method": "max"
          "layer_name": "color",
          "attribute_name": "color",
      },
      {
          "converter": "keypoints_hrnet",
          "point_names": [
              "nose", "eye_l", "eye_r", "ear_l", "ear_r"
          ],
          "point_connections": [
              "nose", "eye_l", "nose", "eye_r", "eye_l", "ear_l", "eye_r", "ear_r"
          ]
      },
      {
          "converter": "keypoints_openpose",
          "point_names": [
              "nose", "eye_l", "eye_r", "ear_l", "ear_r"
          ],
          "point_connections": [
              "nose", "eye_l", "nose", "eye_r", "eye_l", "ear_l", "eye_r", "ear_r"
          ]
      },
      {
          "layer_name": "output",
          "converter": "audio_labels",
          "labels": [
              {
                  "index": 0,
                  "label": "Dog",
                  "threshold": 0.0
              },
              ...
              {
                  "index": 52,
                  "label": "Speech",
                  "threshold": 0.0
              }
          ]
      }
   ]
   ...

.. toctree::
   :maxdepth: 2

   how_to_create_model_proc_file