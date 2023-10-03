.. index:: pair: class; dlstreamer::ImageLayout
.. _doxid-classdlstreamer_1_1_image_layout:

class dlstreamer::ImageLayout
=============================

.. toctree::
	:hidden:

	enum_dlstreamer_ImageLayout_Value.rst




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <image_info.h>
	
	class ImageLayout {
	public:
		// enums
	
		enum :ref:`Value<doxid-classdlstreamer_1_1_image_layout_1ad4e006ff101d882ea06f6fba5dd6172f>`;

		// construction
	
		:target:`ImageLayout<doxid-classdlstreamer_1_1_image_layout_1ad648a85d78fdde08ce12cde67f7a4cbb>`();
		:target:`ImageLayout<doxid-classdlstreamer_1_1_image_layout_1aad0a3654b84986ced0a43c3544033887>`(:ref:`Value<doxid-classdlstreamer_1_1_image_layout_1ad4e006ff101d882ea06f6fba5dd6172f>` value);
		:target:`ImageLayout<doxid-classdlstreamer_1_1_image_layout_1a817cc447c2adf9ba775e0f06fda58719>`(const std::string& str);
		:target:`ImageLayout<doxid-classdlstreamer_1_1_image_layout_1a3e8f09693f017499b39a11d2c1e32511>`(std::vector<size_t> shape);

		// methods
	
		:target:`operator Value<doxid-classdlstreamer_1_1_image_layout_1a4272acb3c60905b09e28fd2f3f4a51e7>` () const;
		:target:`operator bool<doxid-classdlstreamer_1_1_image_layout_1afe4ef3c6d39738361dce7f9aedf4a4c4>` ();
		std::string :target:`to_string<doxid-classdlstreamer_1_1_image_layout_1af93795bd0f00ebe33ed32028d41f26d7>`() const;
		int :target:`w_position<doxid-classdlstreamer_1_1_image_layout_1a78f58325a5b8f324f83614ea4ad2daec>`() const;
		int :target:`h_position<doxid-classdlstreamer_1_1_image_layout_1a7c36b6883913868152d5e072d43c1fb2>`() const;
		int :target:`c_position<doxid-classdlstreamer_1_1_image_layout_1a4248d8e2aa3e0088ce644c946235dcc6>`() const;
		int :target:`n_position<doxid-classdlstreamer_1_1_image_layout_1a27402d42a59dd95e522253036ac7567e>`() const;
	};
