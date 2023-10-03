gvawatermark
============

Overlays the metadata on the video frame to visualize the inference
results.

.. code-block:: none

  Pad Templates:
    SINK template: 'sink'
      Availability: Always
      Capabilities:
        video/x-raw
                  format: { (string)BGRx, (string)BGRA, (string)BGR, (string)NV12, (string)I420 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]
        video/x-raw(memory:DMABuf)
                  format: { (string)RGBA, (string)I420 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]
        video/x-raw(memory:VASurface)
                  format: { (string)NV12 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]

    SRC template: 'src'
      Availability: Always
      Capabilities:
        video/x-raw
                  format: { (string)BGRx, (string)BGRA, (string)BGR, (string)NV12, (string)I420 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]
        video/x-raw(memory:DMABuf)
                  format: { (string)RGBA, (string)I420 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]
        video/x-raw(memory:VASurface)
                  format: { (string)NV12 }
                    width: [ 1, 2147483647 ]
                  height: [ 1, 2147483647 ]
                framerate: [ 0/1, 2147483647/1 ]

  Element has no clocking capabilities.
  Element has no URI handling capabilities.

  Pads:
    SINK: 'sink'
      Pad Template: 'sink'
    SRC: 'src'
      Pad Template: 'src'

  Element Properties:
    async-handling      : The bin will handle Asynchronous state changes
                          flags: readable, writable
                          Boolean. Default: false
    device              : Supported devices are CPU and GPU. Default is CPU on system memory and GPU on video memory
                          flags: readable, writable
                          String. Default: null
    message-forward     : Forwards all children messages
                          flags: readable, writable
                          Boolean. Default: false
    name                : The name of the object
                          flags: readable, writable
                          String. Default: "gvawatermark0"
    parent              : The parent of the object
                          flags: readable, writable
                          Object of type "GstObject"
