Ubuntu advanced installation - compilation from source files
============================================================

The easiest way to install Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework is installing it from pre-built Debian packages with one-click script. 
If you would like to follow this way, please go to :doc:`../../get_started/install/install_guide_ubuntu`.

The instruction below focuses on installation steps with building Intel® DL Streamer Pipeline Framework from the source code
provided in `repository <https://github.com/dlstreamer/dlstreamer>`__.


Step 1: Install prerequisites
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Please go through prerequisites 1 & 2 described in :doc:`../../get_started/install/install_guide_ubuntu`


Step 2: Clone Intel® DL Streamer repository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

First, clone this repository into folder ``~/intel/dlstreamer_gst``:

.. code:: sh

   mkdir -p ~/intel
   git clone --recursive https://github.com/dlstreamer/dlstreamer.git ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst


Step 3: Install Intel® Distribution of OpenVINO™ Toolkit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`Follow OpenVINO™ Toolkit instruction guide here <https://docs.openvino.ai/2024/get-started/install-openvino/install-openvino-archive-linux.html>`__ to install OpenVINO™ on Linux.

* Environment: **Runtime**
* Operating System: **Linux**
* Version: **Latest**
* Distribution: **OpenVINO™ Archives**

After successful OpenVINO™ Toolkit package installation, run the
following commands to install OpenVINO™ Toolkit dependencies and enable
OpenVINO™ Toolkit development environment:

.. code:: sh

   sudo -E /opt/intel/openvino_2024/install_dependencies/install_openvino_dependencies.sh
   source /opt/intel/openvino_2024/setupvars.sh

Install Open Model Zoo tools:

.. code:: sh

   python3 -m pip install --upgrade pip
   python3 -m pip install openvino-dev[onnx,tensorflow,pytorch]

.. note::
   Make sure your environment variable $PATH includes '$HOME/.local/bin' .


Step 4: Install Intel® DL Streamer Pipeline Framework dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install build dependencies:

.. code:: sh

   # Install dependencies
   sudo apt-get update && sudo apt-get install curl wget gpg software-properties-common cmake build-essential libpython3-dev python-gi-dev libopencv-dev jq libgflags-dev libdrm-dev

Download pre-built Debian packages for GStreamer from `GitHub Release page <https://github.com/dlstreamer/dlstreamer/releases>`. 
You can manually download all packages from the release page or try to use following command. 
Install GStreamer from downloaded packages:

A. For **Ubuntu 24.04**:
   
   .. code:: sh

      wget $(wget -q -O - https://api.github.com/repos/dlstreamer/dlstreamer/releases/latest | \
        jq -r '.assets[] | select(.name | contains ("ubuntu_24.04_amd64.deb")) | .browser_download_url')
      sudo apt install -y ./intel-dlstreamer-gst*
      sudo apt install -y ./intel-dlstreamer-ffmpeg*

B. For **Ubuntu 22.04**:

   .. code:: sh

      wget $(wget -q -O - https://api.github.com/repos/dlstreamer/dlstreamer/releases/latest | \
        jq -r '.assets[] | select(.name | contains ("ubuntu_22.04_amd64.deb")) | .browser_download_url')
      sudo apt install -y ./intel-dlstreamer-gst*
      sudo apt install -y ./intel-dlstreamer-ffmpeg*


Step 5: Install OpenCV
^^^^^^^^^^^^^^^^^^^^^^

Download Ninja build system and use it to build OpenCV library:

.. code:: sh

   mkdir -p ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst
   sudo apt-get install ninja-build unzip
   wget -q --no-check-certificate -O opencv.zip https://github.com/opencv/opencv/archive/4.10.0.zip
   unzip opencv.zip && rm opencv.zip && mv opencv-4.10.0 opencv && mkdir -p opencv/build
   cd ./opencv/build
   cmake -DBUILD_TESTS=OFF -DBUILD_PERF_TESTS=OFF -DBUILD_EXAMPLES=OFF -DBUILD_opencv_apps=OFF -GNinja .. \
   && ninja -j "$(nproc)" && sudo ninja install
   

Step 6: Install Python dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you intend to use Python elements or samples, you need to install the
necessary dependencies using the following commands:

-  If you want to set up a local environment follow this step (skip to
   install all the dependencies globally):

   -  Install the ``virtualenv`` tool to create isolated Python
      environments

      .. code:: sh

         # you can install it within the global python interpreter
         python3 -m pip install virtualenv
         # or you can install it as a user package
         python3 -m pip install --user virtualenv

   -  Create a virtual environment and activate it

      .. code:: sh

         cd ~/intel/dlstreamer_gst
         virtualenv -p /usr/bin/python3 .env3 --system-site-packages
         source .env3/bin/activate

-  Install Python requirements:

   .. code:: sh

      cd ~/intel/dlstreamer_gst
      python3 -m pip install --upgrade pip
      python3 -m pip install -r requirements.txt

.. _install-opencl:


Step 7: Install OpenCL™
^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

Run the following commands to install OpenCL™ driver:

.. code:: sh

   # Install
   sudo apt-get update && sudo apt-get install -y intel-opencl-icd ocl-icd-opencl-dev opencl-clhpp-headers


Step 8: Install message brokers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

Installation of message brokers will enable capability of
``gvametapublish`` element to publish inference results to Kafka or
MQTT. Note that ``gvametapublish`` element will be able to publish
inference results to file even if you skip this step.

Run following script to install the message brokers:

.. code:: sh

   cd ~/intel/dlstreamer_gst/scripts/
   sudo -E ./install_metapublish_dependencies.sh

In order to enable one of these message brokers in Pipeline Framework,
corresponding key should be passed to cmake in configuration step. To
enable MQTT please pass ``-DENABLE_PAHO_INSTALLATION=ON`` option to
cmake. To enable Kafka please pass ``-DENABLE_RDKAFKA_INSTALLATION=ON``
option to cmake.


Step 9: Install Intel® oneAPI DPC++/C++ Compiler
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.. note::
   Optional step

:ref:`OpenCL™ driver installation <install-opencl>` is required before continuing.

Intel® oneAPI DPC++ Compiler will enable execution of ``gvawatermark``
and ``gvatrack`` elements on GPU.

.. code:: sh

   # Register Intel® oneAPI APT repository
   curl -fsSL https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB | sudo gpg --dearmor --output /usr/share/keyrings/intel-sw-products.gpg
   echo "deb [signed-by=/usr/share/keyrings/intel-sw-products.gpg] https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/intel-oneapi.list

   # Install Intel® oneAPI DPC++/C++ Compiler
   sudo apt-get update && sudo apt-get install -y intel-oneapi-compiler-dpcpp-cpp intel-level-zero-gpu level-zero-dev

   # Set up environment
   source /opt/intel/oneapi/compiler/latest/env/vars.sh


Step 10: Install VA-API dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

:ref:`OpenCL™ driver installation <install-opencl>` is required before continuing.

To enable VA-API preprocessing of Pipeline Framework's inference
elements run the following commands:

.. code:: sh

   sudo apt-get install -y intel-dlstreamer-gst-vaapi libva-dev vainfo intel-media-va-driver-non-free
   export LIBVA_DRIVER_NAME=iHD
   
   # When using Media, GPU or NPU devices as non-root user, please configure:
   sudo usermod -a -G video <username>	
   sudo usermod -a -G render <username>	

   # Check installation
   vainfo

The output shouldn't contain any error messages, iHD driver must be found.
If no errors occur, please proceed further to the next step.

If you receive error message like the one below, please reboot your
machine and try again.

.. code:: sh

   libva info: va_openDriver() returns -1
   vaInitialize failed with error code -1 (unknown libva error), exit

If you receive any other errors, please retry installation process.
If it's not resolved even after re-installation, please submit an issue for support on GitHub
`here <https://github.com/dlstreamer/dlstreamer/issues>`__.

Additionally, pass ``-DENABLE_VAAPI=ON`` option to cmake in configuration step.


Step 11: Build Intel® DL Streamer Pipeline Framework
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

With all dependencies installed, proceed to build Pipeline Framework:

.. code:: sh

   # OpenVINO™ Toolkit environment
   source /opt/intel/openvino_2024/setupvars.sh
   # GStreamer environment
   source /opt/intel/dlstreamer/gstreamer/setupvars.sh
   # Intel® oneAPI DPC++/C++ Compiler environment (if installed)
   source /opt/intel/oneapi/compiler/latest/env/vars.sh

   export CPATH=/opt/intel/dlstreamer/include:${CPATH}

   # cmake, remove -DENABLE_VAAPI option if VA-API not installed
   mkdir ~/intel/dlstreamer_gst/build
   cd ~/intel/dlstreamer_gst/build
   cmake -DENABLE_VAAPI=ON ..

   # make
   make -j
   
   # Setup Intel® DL Streamer Pipeline Framework environment
   source ~/intel/dlstreamer_gst/scripts/setup_env.sh

When using Media, GPU or NPU devices as non-root user, please configure:

.. code:: sh
   
   sudo usermod -a -G video <username>	
   sudo usermod -a -G render <username>	

Intel® DL Streamer Pipeline Framework is now ready to use!

.. note::
   The environment variables are removed when you close the shell.
   Before each run of Intel® DL Streamer you need to setup the 
   environment with the following 2 scripts as above in this step: 
   ``source /opt/intel/openvino_2024/setupvars.sh``
   and ``source ~/intel/dlstreamer_gst/scripts/setup_env.sh``.
   As an option, you can set the environment variables in file
   ``~/.bashrc`` for automatic enabling.

.. note::
   The manual installation on the host machine may have environment issues.
   If this happened, please consider other ways.
   Also, you can create an issue on GitHub
   `here <https://github.com/dlstreamer/dlstreamer/issues>`__.


Step 12: Intel® DL Streamer installation verification 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Intel® DL Streamer has been installed. Please run the `gst-inspect-1.0 gvadetect` to confirm that GStreamer and Intel® DL Streamer are running

.. code:: sh

    user@my-host:~/intel/dlstreamer_gst/build$ gst-inspect-1.0 gvadetect

If your can see the documentation of ``gvadetect`` element, the installation process is completed.

.. image:: gvadetect_sample_help.png


Step 13: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../../get_started/tutorial`


-----

.. include:: ../../include/disclaimer_footer.rst

