Install Guide Ubuntu
====================

The easiest way to install Intel® Deep Learning Streamer (Intel® DL Streamer) Pipeline Framework is installing :ref:`from pre-built Debian packages <2>` with one-click installation script.
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


Step 4: Further information
^^^^^^^^^^^^^^^^^^^^^^^^^^^
For more information or in case of installation issues, please take a look on detailed documentation available in Developer guide: :doc:`../../dev_guide/advanced_install/advanced_install_guide_prerequisites`



.. _2:

Option #1: Install Intel® DL Streamer Pipeline Framework from Debian packages
-----------------------------------------------------------------------------

Step 1: Download the installation script
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..  code:: sh

   cd ~/intel/dlstreamer_gst/
   wget https://github.com/dlstreamer/dlstreamer/raw/master/scripts/DLS_install_deb_packages.sh


Step 2: Give the script execute permission
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code:: sh

   sudo chmod +x DLS_install_deb_packages.sh


Step 3: Execute the script and follow its instructions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

..  code:: sh
   
   ./DLS_install_deb_packages.sh


.. note::
   For more information or in case of installation issues, please take a look on detailed documentation available in Developer guide: :doc:`../../dev_guide/advanced_install/advanced_install_guide_prebuilt`


Step 4: Next steps - running sample Intel® DL Streamer pipelines
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You are ready to use Intel® DL Streamer. For further instructions to run sample pipeline(s), please go to: :doc:`../tutorial`

.. note::
   The installation script initializes the environment with the 2 scripts listed below. It also provides the option
   to add them to ``~/.profile``. If you did not want to add them, please remember the environment is reset when you close the shell.
   Therefore, before each run of Intel® DL Streamer you need to setup the environment with the 2 scripts listed below.
   
   .. code:: sh

      # Setup OpenVINO™ Toolkit environment
      source /opt/intel/openvino_2024/setupvars.sh
      # Setup GStreamer and Intel® DL Streamer Pipeline Framework environments
      source /opt/intel/dlstreamer/setupvars.sh




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
By default , the latest docker image points to Ubuntu24 version.

For **Ubuntu 24.04** please use **latest** tag or specified version e.g. **2024.1.2-ubuntu24**

.. code:: sh

   docker pull intel/dlstreamer:latest

For **Ubuntu 22.04** please specify tag e.g. **2024.1.2-ubuntu22**

.. code:: sh

   docker pull intel/dlstreamer:2024.1.2-ubuntu22


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


-----

.. include:: ../../include/disclaimer_footer.rst
