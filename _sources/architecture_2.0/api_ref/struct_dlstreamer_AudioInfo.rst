.. index:: pair: struct; dlstreamer::AudioInfo
.. _doxid-structdlstreamer_1_1_audio_info:

struct dlstreamer::AudioInfo
============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <audio_info.h>
	
	struct AudioInfo {
		// construction
	
		:target:`AudioInfo<doxid-structdlstreamer_1_1_audio_info_1a54016fb745c47f8553ed26e693491847>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info);

		// methods
	
		size_t :target:`samples<doxid-structdlstreamer_1_1_audio_info_1a79c13782182f9313f19cd65aee2e8bc6>`();
		size_t :target:`channels<doxid-structdlstreamer_1_1_audio_info_1aa2ee3c6f8d5a0fb4880770e726d4c24a>`();
	};
