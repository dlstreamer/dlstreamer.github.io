============================================
① Memory Interop and C++ abstract interfaces
============================================

Intel® DL Streamer provides independent sub-component for zero-copy buffer sharing and memory interop between various
frameworks and memory handles on CPU and GPU

* CPU memory ``void*``
* FFmpeg ``AVFrame``
* GStreamer ``GstBuffer`` and ``GstMemory``
* Level-Zero ``USM pointers``
* OpenCL ``cl_mem``
* OpenCV ``cv::Mat``
* OpenCV ``cv::UMat``
* OpenVINO™ ``ov::Tensor`` and ``ov::RemoteTensor``
* SYCL ``USM pointers``
* VA-API ``VASurfaceID``

The memory interop sub-component is available via APT installation ``sudo apt install intel-dlstreamer-cpp`` and on
`github https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/include/dlstreamer>`__.

.. note::
  This sub-component implemented as C++ header-only library. Python bindings for this library coming in next releases.

Why memory interop library?
---------------------------

Each media and compute framework with accelerators support (GPU, VPU) defines own interfaces for device and context creation,
memory allocation and task submission. Most frameworks also expose export/import interfaces to convert memory objects
to/from other memory handles:

* High-level media frameworks (FFmpeg, GStreamer) support conversion to/from
  low-level media handles (VA-API and DirectX surfaces)
* Low-level media interfaces (VA-API, DirectX) support conversion to/from
  OS-specific general-purpose GPU memory handles such as DMA buffers on Linux
  and NT handles on Windows
* OpenCL 3.0 recently introduced extension for DMA buffers and NT handles import and export
* Intel® oneAPI Level Zero support conversion between USM device pointers (accessible on GPU only)
  and DMA buffers / NT handles

Together these interfaces allow zero-copy memory sharing between media
operations submitted via media frameworks and SYCL/OpenCL compute kernels submitted
into SYCL/OpenCL queue, assuming media and compute queues created on same physical GPU device.

Despite multiple stages of memory handles conversion (FFmpeg/GStreamer,
VA-API/DirectX, DMA/NT, Level-Zero, SYCL), all converted memory handles refer
to same physical memory block. Thus writing data into one memory handle makes
the data available in all other memory handles, assuming proper synchronization
between write and read operations.

Below is reference to some low-level interfaces used by Intel® DL Streamer memory interop sub-components for zero-copy
buffer sharing between media frameworks and OpenCL/SYCL

1. (Linux) `VA-API to DMA-BUF <http://intel.github.io/libva/group__api__core.html#ga404be4f513f3a15b9a831ff561b1b179>`_
2. `DMA-BUF or NT-Handle to Level-zero <https://oneapi-src.github.io/level-zero-spec/level-zero/latest/core/PROG.html#external-memory-import-and-export>`_
3. `OpenCL extension cl_khr_external_memory <https://registry.khronos.org/OpenCL/specs/3.0-unified/html/OpenCL_API.html#cl_khr_external_memory>`_

Memory interop in a few lines - using Intel® DL Streamer
--------------------------------------------------------

Intel® DL Streamer hides complexity of dealing with low-level interfaces and greatly simplifies memory interop by
defining abstract interfaces :doc:`Tensor <api_ref/class_dlstreamer_Tensor>` and :doc:`MemoryMapper <api_ref/class_dlstreamer_MemoryMapper>`,
and providing header-only implementation of the ```Tensor``` interface for various frameworks and ```MemoryMapper``` implementation
for all technically feasible zero-copy mappings on CPU and GPU and mappings between CPU and GPU:

.. graphviz::
  :caption: Memory interop diagram

  digraph {
    node[shape=record,style=filled,fillcolor=lightskyblue1]

    Gst->CPU
    Gst->DMA
    Gst->OpenCL
    Gst->VAAPI
    DMA->USM
    USM->DMA
    DMA->OpenCL
    OpenCL->CPU
    OpenCL->DMA
    CPU->OpenCV
    OpenCL->OpenCV_UMat
    CPU->OpenVino
    OpenCL->OpenVino
    OpenVino->CPU
    VAAPI->OpenVino
    USM->CPU
    DMA->VAAPI
    VAAPI->DMA
    FFmpeg->VAAPI
    FFmpeg->CPU
  }

All memory mappers implemented under unified interface :doc:`MemoryMapper <api_ref/class_dlstreamer_MemoryMapper>`
with :doc:`TensorPtr <api_ref/class_dlstreamer_TensorPtr>` or :doc:`FramePtr <api_ref/class_dlstreamer_FramePtr>`
as input parameter, but each mapper from framework ``AAA`` to framework ``BBB`` internally casts input pointer to specific
class ``AAA`` Tensor / ``AAA`` Frame and creates output as specific class ``BBB`` Tensor / ``BBB`` Frame,
see table below for each supported framework/library:

.. list-table::
   :header-rows: 1

   * - Framework / Library
     - Native memory object
     - Class implementing :doc:`Tensor <api_ref/class_dlstreamer_Tensor>`
     - Class implementing :doc:`Frame <api_ref/class_dlstreamer_Frame>`
   * - CPU (no framework)
     - void*
     - :doc:`CPUTensor <api_ref/class_dlstreamer_CPUTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`
   * - FFmpeg
     - AVFrame
     -
     - :doc:`FFmpegFrame <api_ref/class_dlstreamer_FFmpegFrame>`
   * - GStreamer
     - GstMemory, GstBuffer
     - :doc:`GSTTensor <api_ref/class_dlstreamer_GSTTensor>`
     - :doc:`GSTFrame <api_ref/class_dlstreamer_GSTFrame>`
   * - Level-zero
     - void*
     - :doc:`USMTensor <api_ref/class_dlstreamer_USMTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`
   * - OpenCL
     - cl_mem
     - :doc:`OpenCLTensor <api_ref/class_dlstreamer_OpenCLTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`
   * - OpenCV
     - cv::Mat
     - :doc:`OpenCVTensor <api_ref/class_dlstreamer_OpenCVTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`
   * - OpenCV
     - cv::UMat
     - :doc:`OpenCVUMatTensor <api_ref/class_dlstreamer_OpenCVUMatTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`
   * - OpenVINO™
     - ov::Tensor
     - :doc:`OpenVINOTensor <api_ref/class_dlstreamer_OpenVINOTensor>`
     - :doc:`OpenVINOFrame <api_ref/class_dlstreamer_OpenVINOFrame>`
   * - SYCL
     - void*
     - :doc:`SYCLUSMTensor <api_ref/class_dlstreamer_SYCLUSMTensor>`
     - :doc:`(BaseFrame) <api_ref/class_dlstreamer_BaseFrame>`

Application can create ``Tensor`` and ``Frame`` objects by either passing pre-allocated native memory object to C++ constructor
(wrap already allocated object) or passing allocation parameters to C++ constructor (allocate new memory).

Many examples how to allocate memory and create and use memory mappers can be found by searching word ``mapper`` in
`samples https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples>`__ and
`src https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/src>`__ folders on github source code, for example
FFmpeg+DPCPP sample `rgb_to_grayscale https://github.com/open-edge-platform/edge-ai-libraries/tree/main/libraries/dl-streamer/samples/ffmpeg_dpcpp/rgb_to_grayscale>`_
and almost every C++ element.

There is special mapper :doc:`MemoryMapperChain <api_ref/class_dlstreamer_MemoryMapperChain>` implementing
unified interface :doc:`MemoryMapper <api_ref/class_dlstreamer_MemoryMapper>` as arbitrary chain of multiple mappers.
As examples, FFmpeg to DPC++/USM is chain of the following mappers

.. graphviz::
  :caption: FFmpeg to USM memory mappers chain

  digraph {
    rankdir="LR"
    node[shape=record,style=filled,fillcolor=lightskyblue1]

    USM0[label="USM (Level-zero)"]
    USM1[label="USM (DPC++)"]

    FFmpeg->VAAPI->DMA->USM0->USM1
  }

and GStreamer to OpenCV UMat is chain of the following mappers

.. graphviz::
  :caption: Gst to USM memory mappers chain

  digraph {
    rankdir="LR"
    node[shape=record,style=filled,fillcolor=lightskyblue1]

    UMat[label="OpenCV cv::UMat"]

    Gst->VAAPI->DMA->OpenCL->UMat
  }

Abstract interfaces for C++ elements
------------------------------------

Additionally, this Intel® DL Streamer sub-component defines abstract interfaces :doc:`Source <api_ref/class_dlstreamer_Source>` ,
:doc:`Transform <api_ref/class_dlstreamer_Transform>` and :doc:`Sink <api_ref/class_dlstreamer_Sink>` used as base interfaces
for all C++ and GStreamer elements. These interfaces take unified pointers to
:doc:`Tensor <api_ref/class_dlstreamer_Tensor>` and :doc:`Frame <api_ref/class_dlstreamer_Frame>`
objects as input and output parameters in functions `read`, `process`, `write` and allow to easily build chain of
multiple operations.
See next page :doc:`C++ elements <cpp_elements>` for details.

How to use in CMake build system
--------------------------------

If application uses Intel® DL Streamer memory interop library and application based on cmake build system, add ``pkg_check_modules``
and ``include_directories`` statements like below:

.. code-block:: none

  pkg_check_modules(DLSTREAMER dl-streamer REQUIRED)
  include_directories(${DLSTREAMER_INCLUDE_DIRS})

For each framework involved in memory interop, add corresponding ``include_directories`` and ``link_libraries`` statements as
required/documented by framework. For example if using memory interop with OpenVINO™, cmake file should contain lines like below

.. code-block:: none

  find_package(OpenVINO COMPONENTS runtime)
  include_directories(${OpenVINO_INCLUDE_DIRS})
  link_libraries(openvino::runtime)

Files structure
---------------

Abstract interfaces are defined in the following header files and installed by ``sudo apt install intel-dlstreamer-cpp``
under folder ``/opt/intel/dlstreamer/include/dlstreamer``:

.. code-block:: none

  include/dlstreamer
  ├── audio_info.h
  ├── context.h
  ├── dictionary.h
  ├── element.h
  ├── frame.h
  ├── frame_info.h
  ├── image_info.h
  ├── image_metadata.h
  ├── memory_mapper_factory.h
  ├── memory_mapper.h
  ├── memory_type.h
  ├── metadata.h
  ├── sink.h
  ├── source.h
  ├── tensor.h
  ├── tensor_info.h
  ├── transform.h
  └── utils.h

The following header files implement :doc:`Tensor <api_ref/class_dlstreamer_Tensor>` interface memory objects in various frameworks and
:doc:`MemoryMapper <api_ref/class_dlstreamer_MemoryMapper>` for memory mapping between frameworks.
These header files installed under corresponding subfolders of ``/opt/intel/dlstreamer/include/dlstreamer`` by same package ``intel-dlstreamer-cpp``:

.. code-block:: none

  include/dlstreamer
  ├── ffmpeg
  │   ├── mappers
  │   │   └── ffmpeg_to_vaapi.h
  │   ├── context.h
  │   ├── frame.h
  │   └── utils.h
  ├── gst
  │   ├── allocator.h
  │   ├── context.h
  │   ├── dictionary.h
  │   ├── frame_batch.h
  │   ├── frame.h
  │   ├── mappers
  │   │   ├── any_to_gst.h
  │   │   ├── gst_to_cpu.h
  │   │   ├── gst_to_dma.h
  │   │   ├── gst_to_opencl.h
  │   │   └── gst_to_vaapi.h
  │   ├── metadata
  │   │   ├── gva_audio_event_meta.h
  │   │   ├── gva_json_meta.h
  │   │   └── gva_tensor_meta.h
  │   ├── metadata.h
  │   ├── plugin.h
  │   ├── tensor.h
  │   └── utils.h
  ├── level_zero
  │   ├── context.h
  │   ├── mappers
  │   │   ├── dma_to_usm.h
  │   │   └── usm_to_dma.h
  │   └── usm_tensor.h
  ├── opencl
  │   ├── context.h
  │   ├── mappers
  │   │   ├── dma_to_opencl.h
  │   │   ├── opencl_to_cpu.h
  │   │   └── opencl_to_dma.h
  │   ├── tensor.h
  │   ├── tensor_ref_counted.h
  │   └── utils.h
  ├── opencv
  │   ├── context.h
  │   ├── mappers
  │   │   └── cpu_to_opencv.h
  │   ├── tensor.h
  │   └── utils.h
  ├── opencv_umat
  │   ├── context.h
  │   ├── mappers
  │   │   └── opencl_to_opencv_umat.h
  │   ├── tensor.h
  │   └── utils.h
  ├── openvino
  │   ├── context.h
  │   ├── frame.h
  │   ├── mappers
  │   │   ├── cpu_to_openvino.h
  │   │   ├── opencl_to_openvino.h
  │   │   ├── openvino_to_cpu.h
  │   │   └── vaapi_to_openvino.h
  │   ├── tensor.h
  │   └── utils.h
  ├── sycl
  │   ├── context.h
  │   ├── mappers
  │   │   └── sycl_usm_to_cpu.h
  │   └── sycl_usm_tensor.h
  └── vaapi
      ├── context.h
      ├── frame_alloc.h
      ├── frame.h
      ├── mappers
      │   ├── dma_to_vaapi.h
      │   └── vaapi_to_dma.h
      ├── tensor.h
      └── utils.h
