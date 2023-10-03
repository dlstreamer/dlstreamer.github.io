DeepSORT tracking support
=========================

This page contains information about how to build DeepSORT people tracking pipeline
with **Intel® Deep Learning Streamer (Intel® DL Streamer)**.

A few words about DeepSORT
--------------------------

DeepSORT is a *zero-term* tracking algorithm 
based on SORT algorithm with deep learning model usage.

This algorithm like other tracking algorithms uses the common structure:

.. graphviz::
  :caption: DeepSORT structure

  digraph {
    rankdir="LR"
    node[shape=box, style="rounded, filled", fillcolor=white]

    od[label="Object Detection"]
    fe[label="Feature Extraction"]
    id[label="ID Assignment"]

    od -> fe -> id
  }

Various tracking algorithms implement each part differenty,
but generally the pattern remains unchanged.

Object detection
~~~~~~~~~~~~~~~~

Object tracking with Intel® DL Streamer models is a simple task.
To enable this usage we going to use :doc:`gvadetect <../elements/gvadetect>`
element with *yolov5m* model.

Feature extraction
~~~~~~~~~~~~~~~~~~

This part of tracking algorithm is necessary to make ID assignments.
In order to distinguish detected objects from each other,
it is necessary to extract information that will uniquely identify the object via Features.
Features may be presented as combination of various positional or colour characteristics,
for example bounding-box coordinates or colour histogram.

Instead of the histogram, DeepSORT uses embeddings generated with DL models.
The example below uses the *person-reidentification-retail-0287* model from Open Model Zoo to get embeddings.
This model is run using :doc:`gvainference <../elements/gvainference>` element since post-processing is not required
(raw embeddings are fed to ID assignment).

Please note following properties on gvainference:

- ``inference-region=roi-list`` – to perform inference on detections (ROIs) from gvatedect;
- ``object-class=person`` – to perform inference on detections (ROIs) whose class identifier is a person, since the re-identification model for people is used.

Make sure you've indicated ``model-proc`` file with labels list for
*yolo-v5* model in ``gvadetect``. The label list should have *person* label.

ID assignment
~~~~~~~~~~~~~

ID assignment is the heart of any OT algorithm.
It contains the complete logic of the algorithm, parts of which may be the Kalman filter,
Linear assignment algorithm, set of features matching algorithms
(embeddings, IoU, histogram…), or OT memory implementation.

We use `deep-sort-realtime <https://github.com/levan92/deep_sort_realtime>`__
python library inside :doc:`python_object_association <../elements/python_object_association>` element.
We pass bounding-boxes with feature embeddings as an input and
get new adjusted bounding-boxes with unique IDs as an output.

.. note::
   By default we overwrite existing input ROIs with new ROIs' metadata,
   because tracking algorithm gives more accurate bounding-boxes
   and we don't need match original ROIs and updated ones with IoU calculation just to set the *id*.
   If you want to keep them set ``overwrite-roi=false`` property.

Because we want to perform tracking only for *persons* we need to indicate this
with ``object-class=person`` property

The ``person`` label will be saved during overwriting, because ``save-object-class-label`` property is ``true`` by default.
This will work while properties ``object-class`` is *defined*, **and** ``overwrite-roi`` is *true*.


Basic DeepSORT pipeline example
-------------------------------

So, we've just described all three parts of the algorithm and how to implement them
with our elements and now we can write whole pipeline:

.. code:: sh

    gst-launch-1.0 \
    filesrc location=<video.mp4> ! decodebin ! \
    gvadetect model=<yolov5m.xml> model_proc=<yolo-v5.json>! \
    gvainference model=<person-reidentification-retail-0287.xml> \
        inference-region=roi-list object-class="person" ! \
    python_object_association object-class="person" ! \
    opencv_meta_overlay ! \
    videoconvert ! gvafpscounter ! xvimagesink sync=false

``python_object_association`` has several properties to set algorithm's parameters.
You can experiment with them to get maximum from your use-case,
just remember all changes may impact on both performance and accuracy.
