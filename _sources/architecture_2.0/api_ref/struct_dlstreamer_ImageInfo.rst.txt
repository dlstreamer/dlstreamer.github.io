.. index:: pair: struct; dlstreamer::ImageInfo
.. _doxid-structdlstreamer_1_1_image_info:

struct dlstreamer::ImageInfo
============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <image_info.h>
	
	struct ImageInfo {
		// construction
	
		:target:`ImageInfo<doxid-structdlstreamer_1_1_image_info_1a1e67391a76a3c294f8bcbe1a60909865>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info);

		// methods
	
		:ref:`ImageLayout<doxid-classdlstreamer_1_1_image_layout>` :target:`layout<doxid-structdlstreamer_1_1_image_info_1a9755c4a5a4e549b2864d78644ddd5bae>`() const;
		size_t :target:`width<doxid-structdlstreamer_1_1_image_info_1adde7a5661928c4335574c8467fd3d8e6>`() const;
		size_t :target:`height<doxid-structdlstreamer_1_1_image_info_1abe6c4800c3bbd72413b516b431d89c04>`() const;
		size_t :target:`channels<doxid-structdlstreamer_1_1_image_info_1adf3ff31540d5786d0389ecb1698085c5>`() const;
		size_t :target:`batch<doxid-structdlstreamer_1_1_image_info_1a093ee18baba9f192050c91ed39c7b6a0>`() const;
		size_t :target:`width_stride<doxid-structdlstreamer_1_1_image_info_1a30251e603d825bf2f71ff463d9ccc5e4>`() const;
		size_t :target:`height_stride<doxid-structdlstreamer_1_1_image_info_1a8ae534098cc6ba148fcaab4b06ea0df4>`() const;
		size_t :target:`channels_stride<doxid-structdlstreamer_1_1_image_info_1a5119fb032f4ac101061a0220f920856a>`() const;
		const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>` :target:`info<doxid-structdlstreamer_1_1_image_info_1abf4528f01701900098713b9d90389462>`() const;
	};
