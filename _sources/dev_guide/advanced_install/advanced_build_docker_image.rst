Ubuntu advanced installation - build Docker image
============================================================

The easiest way to run DLStreamer in Docker is to pull docker images from DockerHub.
If you would like to follow this way, please go to Option 2 in :doc:`../../get_started/install/install_guide_ubuntu`

The instruction below shows how to build Docker images based on Ubuntu22/24 from DLStreamer Dockerfiles.

Step 1: Install prerequisites
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Please go through Prerequisites described in :doc:`../../get_started/install/install_guide_ubuntu`

Step 2: Download Dockerfiles
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can download these files from the main repository using commands below:


All Dockerfiles are in `DLStreamer GitHub repository <https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/docker>`_.

.. tabs::

    .. tab:: Ubuntu24 debian Dockerfile

        .. code-block:: sh

            wget https://raw.githubusercontent.com/open-edge-platform/edge-ai-libraries/main/libraries/dl-streamer/docker/dlstreamer_ubuntu24.Dockerfile

    .. tab:: Ubuntu22 debian Dockerfile

        .. code-block:: sh

            wget https://raw.githubusercontent.com/open-edge-platform/edge-ai-libraries/main/libraries/dl-streamer/docker/dlstreamer_ubuntu22.Dockerfile

    .. tab:: Ubuntu24 dev Dockerfile

        .. code-block:: sh

            wget https://raw.githubusercontent.com/open-edge-platform/edge-ai-libraries/main/libraries/dl-streamer/docker/dlstreamer_dev_ubuntu24.Dockerfile

    .. tab:: Ubuntu22 dev Dockerfile

        .. code-block:: sh

            wget https://raw.githubusercontent.com/open-edge-platform/edge-ai-libraries/main/libraries/dl-streamer/docker/dlstreamer_dev_ubuntu22.Dockerfile


Step 3: Build Docker image
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This is a temaplate command line which builds a Docker image from the specified Dockerfile using the current directory as the build context

..  code:: sh

   docker build -f <Dockerfile name> -t <name for Docker image> .

This command builds a Docker image from the **dlstreamer_dev_ubuntu22.Dockerfile** assigning it the name **dlstreamer-dev-ubuntu22** using the current directory as the build context

..  code:: sh

   docker build -f dlstreamer_dev_ubuntu22.Dockerfile -t dlstreamer-dev-ubuntu22 .