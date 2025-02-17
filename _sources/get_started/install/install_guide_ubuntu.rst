Install Guide Ubuntu
====================

The easiest way to install Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework is installation :ref:`from Debian packages using APT repository <2>`.
If you prefer containerized environment based on Docker, the Intel® DL Streamer Pipeline Framework :ref:`Docker image <3>` is available as well as Dockerfile to build runtime Docker image.
Regardless of chosen installations process, please follow :ref:`prerequisites <1>`.


For detailed description of installation process, including the option with building Intel® DL Streamer Pipeline Framework from the source code
provided in `repository <https://github.com/dlstreamer/dlstreamer>`__, please follow instructions in: :doc:`../../dev_guide/advanced_install/advanced_install_guide_index`


.. _1:

Prerequisites
-------------

To use GPU and/or NPU as an inference devices or to use graphics hardware encoding/decoding capabilities, it is required to install appropriate drivers.
Please use the script below to detect available device(s) and install these drivers. Please also pay attention to displayed information while the script
has references to other Intel® resources when additional configuration is required. 

Step 1: Download the prerequisites installation script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..  code:: sh

   mkdir -p ~/intel/dlstreamer_gst
   cd ~/intel/dlstreamer_gst/
   wget https://github.com/dlstreamer/dlstreamer/raw/master/scripts/DLS_install_prerequisites.sh


Step 2: Give the script execute permission
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: sh

   sudo chmod +x DLS_install_prerequisites.sh


Step 3: Execute the script and follow its instructions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..  code:: sh
   
   ./DLS_install_prerequisites.sh


.. _2:

Option #1: Install Intel® DL Streamer Pipeline Framework from Debian packages using APT repository
--------------------------------------------------------------------------------------------------

This option provides the simplest installation flow using apt-get install command.

Step 1: Setup repositories
^^^^^^^^^^^^^^^^^^^^^^^^^^

..  tabs::

   ..  tab:: Ubuntu 22

      .. code-block:: sh

          sudo -E wget -O- https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB | gpg --dearmor | sudo tee /usr/share/keyrings/oneapi-archive-keyring.gpg > /dev/null
          sudo wget -O- https://eci.intel.com/sed-repos/gpg-keys/GPG-PUB-KEY-INTEL-SED.gpg | sudo tee /usr/share/keyrings/sed-archive-keyring.gpg > /dev/null
          sudo echo "deb [signed-by=/usr/share/keyrings/sed-archive-keyring.gpg] https://eci.intel.com/sed-repos/$(source /etc/os-release && echo $VERSION_CODENAME) sed main" | sudo tee /etc/apt/sources.list.d/sed.list
          sudo bash -c 'echo -e "Package: *\nPin: origin eci.intel.com\nPin-Priority: 1000" > /etc/apt/preferences.d/sed'
          sudo bash -c 'echo "deb [signed-by=/usr/share/keyrings/oneapi-archive-keyring.gpg] https://apt.repos.intel.com/openvino/2025 ubuntu22 main" | sudo tee /etc/apt/sources.list.d/intel-openvino-2025.list'

   ..  tab:: Ubuntu 24

      .. code-block:: sh

          sudo -E wget -O- https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB | gpg --dearmor | sudo tee /usr/share/keyrings/oneapi-archive-keyring.gpg > /dev/null
          sudo wget -O- https://eci.intel.com/sed-repos/gpg-keys/GPG-PUB-KEY-INTEL-SED.gpg | sudo tee /usr/share/keyrings/sed-archive-keyring.gpg > /dev/null
          sudo echo "deb [signed-by=/usr/share/keyrings/sed-archive-keyring.gpg] https://eci.intel.com/sed-repos/$(source /etc/os-release && echo $VERSION_CODENAME) sed main" | sudo tee /etc/apt/sources.list.d/sed.list
          sudo bash -c 'echo -e "Package: *\nPin: origin eci.intel.com\nPin-Priority: 1000" > /etc/apt/preferences.d/sed'
          sudo bash -c 'echo "deb [signed-by=/usr/share/keyrings/oneapi-archive-keyring.gpg] https://apt.repos.intel.com/openvino/2025 ubuntu24 main" | sudo tee /etc/apt/sources.list.d/intel-openvino-2025.list'


Step 2: Install Intel® DL Streamer Pipeline Framework
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: sh

   sudo apt update
   sudo apt-get install intel-dlstreamer

.. note::

   This step will also install the required dependencies, including OpenVINO™ Toolkit and GStreamer.

   
Check for installed packages and versions.

.. code:: sh

   apt list --installed | grep intel-dlstreamer


To install a specific version run the following command:

.. code:: sh

   sudo apt install intel-dlstreamer=<VERSION>.<UPDATE>.<PATCH>


For example

.. code:: sh

   sudo apt install intel-dlstreamer=2025.0.0


List available versions

.. code:: sh

   sudo apt show -a intel-dlstreamer



Step 3: Run hello_dlstreamer script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The script sets up the required environment variables and runs a sample pipeline to confirm that Intel® DL Streamer is installed correctly. 
During the first run, the script will download the YOLOv11s model from the Ultralytics website along with other required components and convert it to the OpenVINO™ format.


..  code:: sh
   
   /opt/intel/dlstreamer/scripts/hello_dlstreamer.sh


.. note::
   
   To set up Linux with the relevant environment variables every time a new terminal is opened, open ~/.bashrc and add the following lines:

..  code:: sh
   
   export LIBVA_DRIVER_NAME=iHD
   export GST_PLUGIN_PATH=/opt/intel/dlstreamer/build/intel64/Release/lib:/opt/intel/dlstreamer/gstreamer/lib/gstreamer-1.0:/opt/intel/dlstreamer/gstreamer/lib/:
   export LD_LIBRARY_PATH=/opt/intel/dlstreamer/gstreamer/lib:/opt/intel/dlstreamer/build/intel64/Release/lib:/opt/intel/dlstreamer/lib/gstreamer-1.0:/usr/lib:/opt/intel/dlstreamer/build/intel64/Release/lib:/opt/opencv:/opt/openh264:/opt/rdkafka:/opt/ffmpeg:/usr/local/lib/gstreamer-1.0:/usr/local/lib
   export LIBVA_DRIVERS_PATH=/usr/lib/x86_64-linux-gnu/dri
   export GST_VA_ALL_DRIVERS=1
   export PATH=/opt/intel/dlstreamer/gstreamer/bin:/opt/intel/dlstreamer/build/intel64/Release/bin:$PATH


.. _3:

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

Visit <https://hub.docker.com/r/intel/dlstreamer/> Intel® DL Streamer image docker hub to select the most appropriate version.
By default , the latest docker image points to Ubuntu 24 version.

For **Ubuntu 22.04** please specify tag e.g. **2025.0.1-ubuntu22**.
For **Ubuntu 24.04** please use **latest** tag or specified version e.g. **2025.0.1-ubuntu24**.

..  tabs::

   ..  tab:: Ubuntu 22

      .. code-block:: sh

          docker pull intel/dlstreamer:2025.0.1-ubuntu22

   ..  tab:: Ubuntu 24

      .. code-block:: sh

          docker pull intel/dlstreamer:latest


Step 4: Run Intel® DL Streamer Pipeline Framework container
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To confirm that your installation is completed successfully, please run a container

.. code:: sh

   docker run -it --rm intel/dlstreamer:latest

In the container, please run the ``gst-inspect-1.0 gvadetect`` to confirm that GStreamer and Intel® DL Streamer are running

.. code:: sh

   gst-inspect-1.0 gvadetect

If your can see the documentation of ``gvadetect`` element, the installation process is completed.

.. image:: gvadetect_sample_help.png


Step 5: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../tutorial`


-----

.. include:: ../../include/disclaimer_footer.rst
