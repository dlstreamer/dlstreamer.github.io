gvafpscounter
=============

Measures frames per second across multiple streams in a single process.

.. code-block:: none

  Pad Templates:
    SINK template: 'sink'
      Availability: Always
      Capabilities:
        video/x-raw(ANY)
        application/tensor(ANY)
        application/tensors(ANY)

    SRC template: 'src'
      Availability: Always
      Capabilities:
        ANY

  Element has no clocking capabilities.
  Element has no URI handling capabilities.

  Pads:
    SINK: 'sink'
      Pad Template: 'sink'
    SRC: 'src'
      Pad Template: 'src'

  Element Properties:
    interval            : The time interval in seconds for which the fps will be measured
                          flags: readable, writable
                          String. Default: "1"
    name                : The name of the object
                          flags: readable, writable
                          String. Default: "gvafpscounter0"
    parent              : The parent of the object
                          flags: readable, writable
                          Object of type "GstObject"
    qos                 : Handle Quality-of-Service events
                          flags: readable, writable
                          Boolean. Default: false
    read-pipe           : Read FPS data from a named pipe. Create and delete a named pipe.
                          flags: readable, writable
                          String. Default: null
    starting-frame      : Start collecting fps measurements after the specified number of frames have been processed to remove the influence of initialization cost
                          flags: readable, writable
                          Unsigned Integer. Range: 0 - 4294967295 Default: 0
    write-pipe          : Write FPS data to a named pipe. Blocks until read-pipe is opened.
                          flags: readable, writable
                          String. Default: null
