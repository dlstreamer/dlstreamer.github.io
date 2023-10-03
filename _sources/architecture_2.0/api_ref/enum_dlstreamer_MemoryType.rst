.. index:: pair: enum; MemoryType
.. _doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db:

enum dlstreamer::MemoryType
===========================

Enum lists supported memory types. Memory type CPU may work with any CPU-accessible memory buffers, other memory types assume memory allocation on CPU or GPU via underlying framework and data access via framework-specific memory handles, for example cl_mem in OpenCL.

.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <memory_type.h>

	enum MemoryType {
	    :target:`Any<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dbaed36a1ef76a59ee3f15180e0441188ad>`        = 0,
	    :target:`CPU<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba2b55387dd066c5bac646ac61543d152d>`        = 0x1,
	    :target:`USM<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba76c4c8690bfd8d30ff84dfa1eac81cb0>`        = 0x2,
	    :target:`DMA<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba33fd5f6391f2f0cb4c91179d7f521949>`        = 0x10,
	    :target:`OpenCL<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba7982b09a852b37f2afb1227eaf552e47>`     = 0x20,
	    :target:`VAAPI<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dbab80a85e9723eafdfdfb1221ae4bb4bf3>`      = 0x40,
	    :target:`GST<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba65faccc4f5d12243a687cfe2338ab83d>`        = 0x80,
	    :target:`FFmpeg<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dbac6822fecd09163125469db27944e993b>`     = 0x100,
	    :target:`OpenCV<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba5bd4c87976f48e6a53919d53e14025e9>`     = 0x200,
	    :target:`OpenCVUMat<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba17f2c65c47447a125416098f632d1ee2>` = 0x400,
	    :target:`OpenVINO<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba7109a5940b811c36ea2e9aa2cee0527f>`   = 0x8000,
	    :target:`PyTorch<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba95b88f180e9eb5678e0f9ebac2cbe643>`    = 0x10000,
	    :target:`TensorFlow<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba074dd699710da0ec1eb45f13b31788e3>` = 0x20000,
	};

