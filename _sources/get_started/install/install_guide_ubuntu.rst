Install Guide Ubuntu
====================

The easiest way to install Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework is installing :ref:`from pre-built Debian packages <1>`.
If you prefer containerized environment based on Docker, the Intel® DL Streamer Pipeline Framework is also :ref:`available <2>` 
on `DockerHub <https://hub.docker.com/r/intel/dlstreamer>`__:
``docker pull intel/dlstreamer:devel`` for development docker image or ``docker pull intel/dlstreamer:latest`` for runtime docker image.

Alternatively, you can build Intel® DL Streamer Pipeline Framework from the source code
provided in `repository <https://github.com/dlstreamer/dlstreamer>`__, either building directly on host system, or
as a Docker image.

The following table summarizes installation options. You can find
detailed instructions for each installation option by following the
links in the first column of the table.


.. list-table::
   :header-rows: 1

   * - Option
     - Supported OS
     - Notes

   * - :ref:`Install Intel® DL Streamer Pipeline Framework pre-built Debian packages <1>`
     - Ubuntu 22.04
     - \-
   * - :ref:`Pull and run Intel® DL Streamer Pipeline Framework Docker image<2>`
     - Any Linux OS as host system
     - Recommended for containerized environment and when host OS is not supported by the Pipeline Framework installer
   * - :ref:`Compile Intel® DL Streamer Pipeline Framework from sources on host system <3>`
     - Ubuntu 22.04
     - If you want to build Pipeline Framework from source code on host system

.. _1:

Option #1: Install Intel® DL Streamer Pipeline Framework from Debian packages
-----------------------------------------------------------------------------

Available Debian packages
^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :align: left
   :header-rows: 1

   * - Package name
     - Description

   * - intel-dlstreamer-dev
     - Development package - installs runtime on CPU/GPU, C++/Python bindings, samples, development tools
   * - intel-dlstreamer-cpu
     - Runtime on CPU - files required for execution on CPU
   * - intel-dlstreamer-gpu
     - Runtime on GPU - files required for execution on GPU
   * - intel-dlstreamer
     - Runtime on CPU/GPU - files required for execution on CPU and GPU
   * - intel-dlstreamer-dpcpp
     - Additional runtime on GPU - runtime libraries built on Intel® oneAPI DPC++ Compiler. This package installs DPC++ runtime as dependency
   * - python3-intel-dlstreamer
     - Python runtime - installs Intel® DL Streamer Pipeline Framework Python bindings and runtime on CPU/GPU
   * - intel-dlstreamer-cpp
     - C++ bindings
   * - intel-dlstreamer-samples
     - C++ and Python samples demonstrating the use of Intel® DL Streamer Pipeline Framework


Step 1: Install prerequisites
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install dependencies and register additional APT repositories.

..  code:: sh

   # Install dependencies
   sudo apt-get update && sudo apt-get install curl wget gpg software-properties-common

   # Register Intel® oneAPI APT repository
   curl -fsSL https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB | sudo gpg --dearmor --output /usr/share/keyrings/intel-sw-products.gpg
   echo "deb [signed-by=/usr/share/keyrings/intel-sw-products.gpg] https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/intel-oneapi.list

   # Download Intel® Graphics APT repository key
   curl -fsSL https://repositories.intel.com/graphics/intel-graphics.key | sudo gpg --dearmor --output /usr/share/keyrings/intel-graphics.gpg


For Intel® Graphics APT repository please use **only one** of following (more information https://dgpu-docs.intel.com/driver/installation.html):

-  For Intel® Data Center GPU Flex Series and Intel® Data Center GPU Max Series:
   
   ..  code:: sh
   
     # Register Intel® Graphics APT repository
     echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/gpu/ubuntu jammy/production/2328 unified" | sudo tee /etc/apt/sources.list.d/intel-graphics.list

-  For Intel® Arc™ GPUs:
   
   ..  code:: sh
   
     # Register Intel® Graphics APT repository
     echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/gpu/ubuntu jammy client" | sudo tee /etc/apt/sources.list.d/intel-graphics.list


Install Intel® oneAPI DPC++/C++ Compiler runtime package and Intel® DL Streamer features based on DPC++:

.. code:: sh

   # Install
   sudo apt-get update && sudo apt-get install intel-level-zero-gpu level-zero

You can additionally install full Intel® oneAPI DPC++/C++ Compiler (previous command installs runtime only):

.. code:: sh

   sudo apt-get install intel-oneapi-compiler-dpcpp-cpp

Step 2: Install Intel® DL Streamer and OpenVINO™ toolkit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Download pre-built Debian packages from `GitHub Release page <https://github.com/dlstreamer/dlstreamer/releases>`. 
You can manually download all packages from the release page or try to use following command:

.. code:: sh

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
   source /opt/intel/openvino_2023/setupvars.sh
   source /opt/intel/dlstreamer/setupvars.sh


Step 3: Install MQTT and Kafka clients for element `gvametapublish`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

In order to enable all `gvametapublish` backends install required dependencies with scripts:

.. code:: sh

   sudo -E /opt/intel/dlstreamer/install_dependencies/install_mqtt_client.sh
   sudo -E /opt/intel/dlstreamer/install_dependencies/install_kafka_client.sh


.. _2:

Option #2: Pull and run Intel® DL Streamer Pipeline Framework Docker image
--------------------------------------------------------------------------

Step 1: Install Docker
^^^^^^^^^^^^^^^^^^^^^^

`Get Docker <https://docs.docker.com/get-docker/>`__ for your host OS

Step 2: Allow connection to X server
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Some Pipeline Framework samples use display. Hence, first run the following
commands to allow connection from Docker container to X server on
host:

.. code:: sh

   xhost local:root
   setfacl -m user:1000:r ~/.Xauthority

Step 3: Run Intel® DL Streamer Pipeline Framework container
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Pull and run the Pipeline Framework container for development:

.. code:: sh

   docker run -it --privileged --net=host \
      --device /dev/dri \
      -v ~/.Xauthority:/home/dlstreamer/.Xauthority \
      -v /tmp/.X11-unix \
      -e DISPLAY=$DISPLAY \
      -v /dev/bus/usb \
      --rm intel/dlstreamer:devel /bin/bash

For deployment, you can download the Pipeline Framework runtime container
with reduced size comparing to development container. Please note
that this container does not have the Pipeline Framework samples:

.. code:: sh

   docker run -it --privileged --net=host \
      --device /dev/dri \
      -v ~/.Xauthority:/home/dlstreamer/.Xauthority \
      -v /tmp/.X11-unix \
      -e DISPLAY=$DISPLAY \
      -v /dev/bus/usb \
      --rm intel/dlstreamer:latest /bin/bash

Inside Docker container for development, you can find the Pipeline Framework
samples in folder
``/opt/intel/dlstreamer/samples``

Before using the Pipeline Framework samples, run the script
``download_models.sh`` (located in ``samples`` folder) to download
the models required for samples.


Step 4: Run Intel® DL Streamer Pipeline Framework container with Intel® oneAPI DPC++/C++ Compiler
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::
   Optional step

To enable execution of ``gvawatermark`` and ``gvatrack``
elements on GPU you should download container with Intel® oneAPI DPC++/C++ Compiler.

.. code:: sh

   docker run -it --privileged --net=host \
      --device /dev/dri \
      -v ~/.Xauthority:/home/dlstreamer/.Xauthority \
      -v /tmp/.X11-unix \
      -e DISPLAY=$DISPLAY \
      -v /dev/bus/usb \
      --rm dlstreamer/dlstreamer:dpcpp /bin/bash

.. _gpu-ubuntu22:

Intel® Graphics Compute Runtime for oneAPI Level Zero and OpenCL™ Driver configuration on Ubuntu* 22.04
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Intel® Graphics Compute Runtime for oneAPI Level Zero and OpenCL™ Driver components are required to use a GPU device.
The driver is installed in the Intel® DL Streamer Pipeline Framework Docker image but you need to activate it in the container for a non-root user if you have Ubuntu 22.04 on your host.

To access GPU capabilities, you need to have correct permissions on the host and Docker container.
Run the following command to list the group assigned ownership of the render nodes on your host:

.. code:: sh

   stat -c "group_name=%G group_id=%g" /dev/dri/render*

Intel® DL Streamer Pipeline Framework Docker images do not contain a render group for `dlstreamer` non-root user because the render group does not have a strict group ID, unlike the video group.
To run container as non-root with access to a GPU device, specify the render group ID from your host:

.. code:: sh

   docker run -it --device /dev/dri --group-add=<render_group_id_on_host> <other_args> <image_name>

For example, get the render group ID on your host:

.. code:: sh

   docker run -it --device /dev/dri --group-add=$(stat -c "%g" /dev/dri/render*) <other_args> <image_name>

Now you can use the container with GPU access under the non-root user.

.. _3:

Option #3: Compile Intel® DL Streamer Pipeline Framework from sources on host system
------------------------------------------------------------------------------------

.. note::
   These instructions are verified on Ubuntu 22.04

Step 1: Clone this repository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

First, clone this repository into folder ``~/intel/dlstreamer_gst``:

.. code:: sh

   mkdir -p ~/intel
   git clone --recursive https://github.com/dlstreamer/dlstreamer.git ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst

Step 2: Install Intel® Distribution of OpenVINO™ Toolkit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`Download OpenVINO™ Toolkit package here <https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/download.html>`__ by selecting:

* Environment: **Runtime**
* Operating System: **Linux**
* Version: **Latest**
* Distribution: **OpenVINO™ Archives**

`Follow OpenVINO™ Toolkit instruction guide here <https://docs.openvino.ai/2023.0/openvino_docs_install_guides_installing_openvino_linux_header.html>`__ to install OpenVINO™ on Linux.

After successful OpenVINO™ Toolkit package installation, run the
following commands to install OpenVINO™ Toolkit dependencies and enable
OpenVINO™ Toolkit development environment:

.. code:: sh

   sudo -E /opt/intel/openvino_2023/install_dependencies/install_openvino_dependencies.sh
   source /opt/intel/openvino_2023/setupvars.sh

Install Open Model Zoo tools:

.. code:: sh

   python3 -m pip install --upgrade pip
   python3 -m pip install openvino-dev[onnx]

Step 3: Install Intel® DL Streamer Pipeline Framework dependencies
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Install build dependencies:

.. code:: sh

   # Install dependencies
   sudo apt-get update && sudo apt-get install curl wget gpg software-properties-common cmake build-essential libpython3-dev python-gi-dev libopencv-dev libva-dev

Download pre-built Debian packages for GStreamer from `GitHub Release page <https://github.com/dlstreamer/dlstreamer/releases>`. 
You can manually download all packages from the release page or try to use following command:

.. code:: sh

   wget $(wget -q -O - https://api.github.com/repos/dlstreamer/dlstreamer/releases/latest | \
     jq -r '.assets[] | select(.name | contains (".deb")) | .browser_download_url')

Install GStreamer:

.. code:: sh

   # Install GStreamer
   sudo apt install -y ./intel-dlstreamer-gst*

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

Register Intel® Graphics APT repository key by:

.. code:: sh

   # Download Intel® Graphics APT repository key
   curl -fsSL https://repositories.intel.com/graphics/intel-graphics.key | sudo gpg --dearmor --output /usr/share/keyrings/intel-graphics.gpg


Then use **only one** of following (more information https://dgpu-docs.intel.com/driver/installation.html):

-  For Intel® Data Center GPU Flex Series and Intel® Data Center GPU Max Series:
   
   ..  code:: sh
   
     # Register Intel® Graphics APT repository
     echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/gpu/ubuntu jammy/production/2328 unified" | sudo tee /etc/apt/sources.list.d/intel-graphics.list

-  For Intel® Arc™ GPUs:
   
   ..  code:: sh
   
     # Register Intel® Graphics APT repository
     echo "deb [arch=amd64 signed-by=/usr/share/keyrings/intel-graphics.gpg] https://repositories.intel.com/gpu/ubuntu jammy client" | sudo tee /etc/apt/sources.list.d/intel-graphics.list

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
   # Check installation
   vainfo

The output shouldn't contain any error messages, iHD driver must be
found. If no errors occur, please proceed further to the next step.

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
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

With all dependencies installed, proceed to build Pipeline Framework:

.. code:: sh

   # OpenVINO™ Toolkit environment
   source /opt/intel/openvino_2023/setupvars.sh
   # GStreamer environment
   source /opt/intel/dlstreamer/gstreamer/setupvars.sh
   # Intel® oneAPI DPC++/C++ Compiler environment (if installed)
   # source /opt/intel/oneapi/compiler/latest/env/vars.sh

   # cmake
   mkdir ~/intel/dlstreamer_gst/build
   cd ~/intel/dlstreamer_gst/build
   cmake ..

   # make
   make -j
   
   # Setup Intel® DL Streamer Pipeline Framework environment
   source ~/intel/dlstreamer_gst/scripts/setup_env.sh

Intel® DL Streamer Pipeline Framework is now ready to use!

You can find samples in folder ``~/intel/dlstreamer_gst/samples``.
Before using the samples, run the script ``download_models.sh`` (located
in ``samples`` folder) to download the models required for samples.

.. note::
   The environment variables are removed when you close the shell.
   As an option, you can set the environment variables in file
   ``~/.bashrc`` for automatic enabling.

.. note::
   The manual installation on the host machine may have environment issues.
   If this happened, please consider other ways.
   Also, you can create an issue on GitHub
   `here <https://github.com/dlstreamer/dlstreamer/issues>`__.

Next Steps
----------

* :doc:`../tutorial`
* `Samples overview <https://github.com/dlstreamer/dlstreamer/blob/master/samples/gstreamer/README.md>`__

-----

.. include:: ../../include/disclaimer_footer.rst

