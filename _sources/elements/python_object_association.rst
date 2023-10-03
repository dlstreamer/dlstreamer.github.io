python_object_association
=========================

ID assignment SORT type tracking algorithm which require embedding from each ROI to cosine comparison.


Please refer to :doc:`DeepSORT support <../dev_guide/deepsort_implementation>` for more
information on usage.

.. code-block:: none

  Pad Templates:
    SINK template: 'sink'
      Availability: Always
      Capabilities:
        video/x-raw
        video/x-raw(memory:DMABuf)
        video/x-raw(memory:VASurface)

    SRC template: 'src'
      Availability: Always
      Capabilities:
        video/x-raw
        video/x-raw(memory:DMABuf)
        video/x-raw(memory:VASurface)

  Element has no clocking capabilities.
  Element has no URI handling capabilities.

  Pads:
    SINK: 'sink'
      Pad Template: 'sink'
    SRC: 'src'
      Pad Template: 'src'

  Element Properties:
    max-age             : Maximum number of missed misses before a track is deleted.
                          flags: readable, writable
                          Integer. Range: 0 - 2147483647 Default: 70
    max-iou-distance    : The matching IoU threshold. Samples with larger distance are considered
                  an invalid match.
                          flags: readable, writable
                          Double. Range:               0 -               1 Default:             0.7
    n-init              : Number of consecutive detections before the track is confirmed. The
                  track state is set to `Deleted` if a miss occurs within the first `n-init` frames.
                          flags: readable, writable
                          Integer. Range: 1 - 2147483647 Default: 3
    name                : The name of the object
                          flags: readable, writable, 0x2000
                          String. Default: "python_object_association+identifier0"
    nn-budget           : Fix samples per class to at most this number. Removes
                  the oldest samples when the budget is reached.
                          flags: readable, writable
                          Integer. Range: 0 - 2147483647 Default: 100
    object-class        : Filter for Region of Interest class label on this element input.
                          flags: readable, writable
                          String. Default: ""
    overwrite-roi       : If True, input ROIs will be overwritten with tracker's output.
                          flags: readable, writable
                          Boolean. Default: true
    parent              : The parent of the object
                          flags: readable, writable, 0x2000
                          Object of type "GstObject"
    qos                 : Handle Quality-of-Service events
                          flags: readable, writable
                          Boolean. Default: false
    save-object-class-label: If True, the label from `object-class` will be saved during ROI overwriting.
                          flags: readable, writable
                          Boolean. Default: true
