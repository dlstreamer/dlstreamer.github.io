Real Sense Plugin
=======================

This guide provides information on how to use **gvarealsense** plugin for obtaining depth and RGB data from RealSense cameras. 
Plugin reads depth and RGB data from the Real Sense camera and provides it in a PCD format suitable for further processing in DL Streamer pipelines.

.. note::
   Validated on Ubuntu 24.04 with kernel version >= 6.12 and Intel® Core™ Ultra Processors - series 2.


1. **Compilation**

To compile the RealSense DL Streamer plugin, you need to have the following dependencies installed:
- `Intel RealSense SDK 2.0 <https://github.com/IntelRealSense/librealsense>`__


Once you have the dependencies installed, to compile DL Streamer with the RealSense plugin, you need to enable the `ENABLE_REALSENSE` option in the CMake configuration.
This can be done by setting the `-DENABLE_REALSENSE=ON` flag when running cmake (`Advanced installation - compilation from source files <https://dlstreamer.github.io/dev_guide/advanced_install/advanced_install_guide_compilation.html>`__).

For full installation procedure, please, refer to the `Deep Learning Streamer Documentation <https://dlstreamer.github.io/get_started/get_started_index.html>`__.


2. **Usage example**

Example pipeline for using the gvarealsense plugin:

.. code:: shell

    gst-launch-1.0 gvarealsense camera=/dev/video0 ! queue ! fakesink dump=true
    


3. **Supported pcd (Point Cloud Data) formats:**

   - ASCII
   - Binary (planned)
   - Compressed Binary (planned)


Example of PCD ASCII output format:

.. code:: shell

    # .PCD v0.7 - Point Cloud Data file format
    VERSION 0.7
    FIELDS x y z
    SIZE 4 4 4
    TYPE F F F
    COUNT 1 1 1
    WIDTH 640
    HEIGHT 480
    VIEWPOINT 0 0 0 1 0 0 0
    POINTS 307200
    DATA ascii
    0.2 0.1 0.3 105 106 117
    ...

    