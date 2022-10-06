.. index:: pair: struct; dlstreamer::ParamDesc
.. _doxid-structdlstreamer_1_1_param_desc:

struct dlstreamer::ParamDesc
============================

.. toctree::
	:hidden:

Structure describing element parameter - name, short description, default value, range or list (for strings) of supported values.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <element.h>
	
	struct ParamDesc {
		// fields
	
		std::string :target:`name<doxid-structdlstreamer_1_1_param_desc_1a287c4c836f650906570d4e22cf591640>`;
		std::string :target:`description<doxid-structdlstreamer_1_1_param_desc_1aaa5120bf44a045324974db258c62d9bc>`;
		:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` :target:`default_value<doxid-structdlstreamer_1_1_param_desc_1a2ff3c74488a0f06a6ecb52b337eeef20>`;
		std::vector<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :target:`range<doxid-structdlstreamer_1_1_param_desc_1a3e26d149e85d4a1172b5b1796dcf2529>`;

		// construction
	
		:target:`ParamDesc<doxid-structdlstreamer_1_1_param_desc_1a8177433883b47ce4728ac475ebebe390>`(
			std::string_view name,
			std::string_view desc,
			:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` default_value,
			std::vector<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> valid_values = {}
		);
	
		:target:`ParamDesc<doxid-structdlstreamer_1_1_param_desc_1a9831932c598994e79114f6958af58e37>`(
			std::string_view name,
			std::string_view desc,
			const :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`& default_value,
			const :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`& min_value,
			const :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`& max_value
		);
	
		:target:`ParamDesc<doxid-structdlstreamer_1_1_param_desc_1ab5b1fddff71e64aec750bf9a59e856ac>`(
			std::string_view name,
			std::string_view desc,
			const char* default_value,
			std::vector<std::string> valid_values = {}
		);

		// methods
	
		template <typename T>
		bool :target:`is_type<doxid-structdlstreamer_1_1_param_desc_1a1c989f5389598d1366f50d1dcc1c5bf6>`() const;
	};
