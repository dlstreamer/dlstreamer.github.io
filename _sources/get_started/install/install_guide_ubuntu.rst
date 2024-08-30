Install Guide Ubuntu
====================

The easiest way to install Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework is installing :ref:`from pre-built Debian packages <3>`.
If you prefer containerized environment based on Docker, the Intel® DL Streamer Pipeline Framework Docker image is available as well as Dockerfile to build runtime Docker image.

Alternatively, you can build Intel® DL Streamer Pipeline Framework from the source code
provided in `repository <https://github.com/dlstreamer/dlstreamer>`__, either building directly on host system, or
as a Docker image. Before running chosen installations process, please follow prerequisites.

.. list-table::
   :header-rows: 1

   * - Prerequisite
     - Notes

   * - :ref:`Install Intel® GPU drivers for computing and media runtimes <1>`
     - \-
   * - :ref:`Install Intel® NPU drivers <2>`
     - Optional step only for Intel® Core™ Ultra processors with NPU AI accelerator.


The following table summarizes installation options. You can find
detailed instructions for each installation option by following the
links in the first column of the table.


.. list-table::
   :header-rows: 1

   * - Option
     - Supported OS
     - Notes

   * - :ref:`Install Intel® DL Streamer Pipeline Framework pre-built Debian packages <3>`
     - Ubuntu 22.04 (kernel 6.6+ for NPU)
     - \-
   * - :ref:`Install Docker image from Docker Hub and run it <4>`
     - Any Linux OS as host system
     - Recommended for containerized environment and when host OS is not supported by the Pipeline Framework installer
   * - :ref:`Compile Intel® DL Streamer Pipeline Framework from sources on host system <5>`
     - Ubuntu 22.04 (kernel 6.6+ for NPU)
     - If you want to build Pipeline Framework from source code on host system


.. _1:

Prerequisite 1 - Intel® GPU drivers for computing and media runtimes
-----------------------------------------------------------------------

To use GPU as an inference device or to use graphics hardware encoding/decoding capabilities, it is required to install GPU computing and media runtime drivers.

A. Install dependencies and register additional APT repositories.

..  code:: sh

   # Install dependencies
   sudo apt-get update && sudo apt-get install curl wget gpg software-properties-common jq

   # Register Intel® oneAPI APT repository
   curl -fsSL https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB | sudo gpg --dearmor --output /usr/share/keyrings/intel-sw-products.gpg
   echo "deb [signed-by=/usr/share/keyrings/intel-sw-products.gpg] https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/intel-oneapi.list


B. Please cheek that you can see a ``renderD*`` device in ``/dev/dri`` directory before installation. You should be able to see a ``renderD128`` for the integrated GPU or ``renderD129`` for the discrete GPU.

   .. code:: sh

      user@my-host:~$ ll /dev/dri | grep renderD
      crw-rw----  1 root render 226, 128 Aug  6 22:41 renderD128
   
   If you can see see the device, please follow the next step C. If you cannot see it, please follow instructions to the full installation processes, including Kernel Mode drivers:
         -  `For Intel® Data Center GPU Flex Series and Intel® Data Center GPU Max Series <https://dgpu-docs.intel.com/driver/installation.html>`__
         -  `For Intel® Arc™ GPUs <https://dgpu-docs.intel.com/driver/client/overview.html>`__

C. To register Intel® Graphics APT repository, please use **only one** of the following according to your hardware:

-  For Intel® Data Center GPU Flex Series and Intel® Data Center GPU Max Series:
   
   ..  code:: sh
   
      # Download Intel® Graphics APT repository key
      wget -qO - https://repositories.intel.com/graphics/intel-graphics.key | sudo gpg --yes --dearmor --output /usr/share/keyrings/intel-graphics.gpg

      # Download Intel® Graphics APT repository
      echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/graphics/ubuntu jammy flex" | sudo tee /etc/apt/sources.list.d/intel-graphics.list

-  For Intel® Client and Arc™ GPUs:
   
   ..  code:: sh
   
       # Download Intel® Graphics APT repository key
      wget -qO - https://repositories.intel.com/gpu/intel-graphics.key | sudo gpg --yes --dearmor --output /usr/share/keyrings/intel-graphics.gpg

      # Download Intel® Graphics APT repository
      echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/gpu/ubuntu jammy client" | sudo tee /etc/apt/sources.list.d/intel-graphics.list

D. Install or update packages responsible for computing and media runtimes:

   .. code:: sh

      # Install
      sudo apt-get update && sudo apt-get install intel-level-zero-gpu level-zero


.. _2:

Prerequisite 2 - Install Intel® NPU drivers
------------------------------------------

.. note::
   Optional step for Intel® Core™ Ultra processors

If you want to use NPU AI accelerator, you need to have Intel® NPU drivers installed.

A. Before installation, please make sure that intel_vpu.ko module is enabled on your host:

.. code:: sh

   user@your-host:~$ lsmod | grep intel_vpu
   intel_vpu             245760  0

B. Installing the driver requires the device to be recognized by your system - Kernel Mode driver should be available. It means you can see a ``accel`` device in ``/dev/dri`` directory. If you don't see it, please reboot the host.

   .. code:: sh

      user@my-host:~$ ll /dev/accel/ | grep accel
      crw-rw----  1 root render 261, 0   Aug  6 22:41 accel0

C. Install the newest Intel® NPU driver. Please follow 'Installation procedure' for the newest available driver version described in: https://github.com/intel/linux-npu-driver/releases

.. note::
   If you are experiencing issues with installation process, check all notes and tips in the release note for the newest Intel® NPU driver version: https://github.com/intel/linux-npu-driver/releases.
   Please pay attention to access to the device as a non-root user.

.. note::
   The following error can be reported when running Intel® DL Streamer on NPU device:

   .. code:: sh

      Setting pipeline to PLAYING ...
      New clock: GstSystemClock
      Caught SIGSEGV
      Spinning.

   In such case, please use the following setting as a temporary workaround:

   .. code:: sh

      export ZE_ENABLE_ALT_DRIVERS=libze_intel_vpu.so

   The issue should be fixed with newer versions of Intel® NPU drivers and Intel® OpenVINO™ NPU plugins.


.. _3:

Option #1: Install Intel® DL Streamer Pipeline Framework from Debian packages
-----------------------------------------------------------------------------

Step 1: Install Intel® DL Streamer and OpenVINO™ toolkit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Download pre-built Debian packages from `GitHub Release page <https://github.com/dlstreamer/dlstreamer/releases>`. 
You can manually download all packages from the release page or try to use following command:

.. code:: sh

   mkdir -p ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst
   wget $(wget -q -O - https://api.github.com/repos/dlstreamer/dlstreamer/releases/latest | \
     jq -r '.assets[] | select(.name | contains (".deb")) | .browser_download_url')

Install Intel® DL Streamer via ``apt install`` and OpenVINO™ via script ``install_openvino.sh``.

..  code:: sh

   # Install Intel® DL Streamer
   sudo apt install ./*.deb

   # Install OpenVINO™ toolkit (if not installed)
   sudo -E /opt/intel/dlstreamer/install_dependencies/install_openvino.sh


Configure the environment after installing Intel® DL Streamer and OpenVINO™:

..  code:: sh

   # Setup OpenVINO™ and Intel® DL Streamer environment
   source /opt/intel/openvino_2024/setupvars.sh
   source /opt/intel/dlstreamer/setupvars.sh


Step 2: Install MQTT and Kafka clients for element `gvametapublish`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

In order to enable all ``gvametapublish`` backends install required dependencies with scripts:

.. code:: sh

   sudo -E /opt/intel/dlstreamer/install_dependencies/install_mqtt_client.sh
   sudo -E /opt/intel/dlstreamer/install_dependencies/install_kafka_client.sh


Step 3: Add user to groups
^^^^^^^^^^^^^^^^^^^^^^^^^^

When using Media, GPU or NPU devices as non-root user, please add your user to `video` and `render` groups:

.. code:: sh
   
   sudo usermod -a -G video <username>	
   sudo usermod -a -G render <username>


Step 4: Set up the environment for Intel® DL Streamer
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Source required environment variables to run GStreamer and Intel® DL Streamer:

.. code:: sh

   # Setup OpenVINO™ Toolkit environment
   source /opt/intel/openvino_2024/setupvars.sh
   # Setup GStreamer environment
   source /opt/intel/dlstreamer/gstreamer/setupvars.sh  
   # Setup Intel® DL Streamer Pipeline Framework environment
   source /opt/intel/dlstreamer/setupvars.sh

.. note::
   The environment variables are removed when you close the shell.
   Before each run of Intel® DL Streamer you need to setup the 
   environment with the 3 scripts listed in this step.
   As an option, you can set the environment variables in file
   ``~/.bashrc`` for automatic enabling.


Step 5: Verify Intel® DL Streamer installation 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Intel® DL Streamer has been installed. You can run the ``gst-inspect-1.0 gvadetect`` to confirm that GStreamer and Intel® DL Streamer are running:

.. code:: sh

   gst-inspect-1.0 gvadetect

If your can see the documentation of ``gvadetect`` element, the installation process is completed.

.. image:: gvadetect_sample_help.png


Step 6: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../tutorial`



.. _4:

Option #2: Install Docker image from Docker Hub and run it
----------------------------------------------------------

Step 1: Install Docker
^^^^^^^^^^^^^^^^^^^^^^

`Get Docker <https://docs.docker.com/get-docker/>`__ for your host OS
 To prevent file permission issues please follow 'Manage Docker as a non-root user' section steps 
 described here <https://docs.docker.com/engine/install/linux-postinstall/>

Step 2: Allow connection to X server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Some Pipeline Framework samples use display. Hence, first run the following
commands to allow connection from Docker container to X server on host:

.. code:: sh

   xhost local:root
   setfacl -m user:1000:r ~/.Xauthority

Step 3: Pull the Intel® DL Streamer Docker image from Docker Hub
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: sh

   docker pull intel/dlstreamer:latest


Step 4: Run Intel® DL Streamer Pipeline Framework container
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To confirm that your installation is completed successfully, please run a container

.. code:: sh

   docker run -it --rm intel/dlstreamer:latest

In the container, please run the ``gst-inspect-1.0 gvadetect`` to confirm that GStreamer and Intel® DL Streamer are running

.. code:: sh

   dlstreamer@ea6445a05788:~$ gst-inspect-1.0 gvadetect

If your can see the documentation of ``gvadetect`` element, the installation process is completed.

.. image:: gvadetect_sample_help.png


Step 5: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../tutorial`


.. _5:

Option #3: Compile Intel® DL Streamer Pipeline Framework from sources on host system
------------------------------------------------------------------------------------

.. note::
   These instructions are verified on Ubuntu 22.04


Step 1: Clone Intel® DL Streamer repository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

First, clone this repository into folder ``~/intel/dlstreamer_gst``:

.. code:: sh

   mkdir -p ~/intel
   git clone --recursive https://github.com/dlstreamer/dlstreamer.git ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst


Step 2: Install Intel® Distribution of OpenVINO™ Toolkit
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


Step 3: Install Intel® DL Streamer Pipeline Framework dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install build dependencies:

.. code:: sh

   # Install dependencies
   sudo apt-get update && sudo apt-get install curl wget gpg software-properties-common cmake build-essential libpython3-dev python-gi-dev libopencv-dev jq libgflags-dev

Download pre-built Debian packages for GStreamer from `GitHub Release page <https://github.com/dlstreamer/dlstreamer/releases>`. 
You can manually download all packages from the release page or try to use following command. 
Install GStreamer from downloaded packages:

.. code:: sh

   wget $(wget -q -O - https://api.github.com/repos/dlstreamer/dlstreamer/releases/latest | \
     jq -r '.assets[] | select(.name | contains (".deb")) | .browser_download_url')
   sudo apt install -y ./intel-dlstreamer-gst*
   sudo apt install -y ./intel-dlstreamer-ffmpeg*


Step 4: Install Python dependencies
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


Step 5: Install OpenCL™
^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

Run the following commands to install OpenCL™ driver:

.. code:: sh

   # Install
   sudo apt-get update && sudo apt-get install -y intel-opencl-icd ocl-icd-opencl-dev opencl-clhpp-headers


Step 6: Install message brokers
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


Step 7: Install Intel® oneAPI DPC++/C++ Compiler
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


Step 8: Install VA-API dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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


Step 9: Build Intel® DL Streamer Pipeline Framework
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

With all dependencies installed, proceed to build Pipeline Framework:

.. code:: sh

   # OpenVINO™ Toolkit environment
   source /opt/intel/openvino_2024/setupvars.sh
   # GStreamer environment
   source /opt/intel/dlstreamer/gstreamer/setupvars.sh
   # Intel® oneAPI DPC++/C++ Compiler environment (if installed)
   source /opt/intel/oneapi/compiler/latest/env/vars.sh

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
   environment with the following 3 scripts as above in this step: 
   ``source /opt/intel/openvino_2024/setupvars.sh``, 
   ``source /opt/intel/dlstreamer/gstreamer/setupvars.sh`` 
   and ``source ~/intel/dlstreamer_gst/scripts/setup_env.sh``.
   As an option, you can set the environment variables in file
   ``~/.bashrc`` for automatic enabling.

.. note::
   The manual installation on the host machine may have environment issues.
   If this happened, please consider other ways.
   Also, you can create an issue on GitHub
   `here <https://github.com/dlstreamer/dlstreamer/issues>`__.


Step 10: Intel® DL Streamer installation verification 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Intel® DL Streamer has been installed. Please run the `gst-inspect-1.0 gvadetect` to confirm that GStreamer and Intel® DL Streamer are running

.. code:: sh

    user@my-host:~/intel/dlstreamer_gst/build$ gst-inspect-1.0 gvadetect

If your can see the documentation of ``gvadetect`` element, the installation process is completed.

.. image:: gvadetect_sample_help.png


Step 11: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../tutorial`


-----

.. include:: ../../include/disclaimer_footer.rst

