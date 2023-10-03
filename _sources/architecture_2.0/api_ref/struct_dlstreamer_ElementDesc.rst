.. index:: pair: struct; dlstreamer::ElementDesc
.. _doxid-structdlstreamer_1_1_element_desc:

struct dlstreamer::ElementDesc
==============================

.. toctree::
	:hidden:

The structure used to register element and create element instance.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <element.h>
	
	struct ElementDesc {
		// fields
	
		int32_t :target:`magic<doxid-structdlstreamer_1_1_element_desc_1a920ea5780c1fb65dc3ed8aab133fb481>` = ElementDescMagic;
		std::string_view :target:`name<doxid-structdlstreamer_1_1_element_desc_1a24d4ba6add6b7bc4e43ea4825e6f1f94>`;
		std::string_view :target:`description<doxid-structdlstreamer_1_1_element_desc_1affa596fdc3d596b2459e59e385c28374>`;
		std::string_view :target:`author<doxid-structdlstreamer_1_1_element_desc_1a23532ac419883efc7813db98eb272657>`;
		:ref:`ParamDescVector<doxid-namespacedlstreamer_1a1c0d94608894c5255d65851870d3a184>`* :target:`params<doxid-structdlstreamer_1_1_element_desc_1a25e2065ba4a9096eddd59cfb2f11d3d4>`;
		:ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :target:`input_info<doxid-structdlstreamer_1_1_element_desc_1a7b673627494f6955291e9ecbc426329c>`;
		:ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :target:`output_info<doxid-structdlstreamer_1_1_element_desc_1a3198a47dd5dc05096a90330e0b4562a9>`;
		const std::function<:ref:`Element<doxid-classdlstreamer_1_1_element>`*(:ref:`DictionaryCPtr<doxid-namespacedlstreamer_1a8407dcbf0aebfcb357acad3ac2d27bfc>` :ref:`params<doxid-structdlstreamer_1_1_element_desc_1a25e2065ba4a9096eddd59cfb2f11d3d4>`, const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`&app_context)> :target:`create<doxid-structdlstreamer_1_1_element_desc_1a5763f6feeecd3b4ab4bfd0cbe06ebfc5>`;
		int :target:`flags<doxid-structdlstreamer_1_1_element_desc_1a1a34808fa322f06e1e2735099c994b66>` = 0;
	};
