.. index:: pair: class; dlstreamer::AffineTransformInfoMetadata
.. _doxid-classdlstreamer_1_1_affine_transform_info_metadata:

class dlstreamer::AffineTransformInfoMetadata
=============================================

.. toctree::
	:hidden:

	struct_dlstreamer_AffineTransformInfoMetadata_key.rst




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <image_metadata.h>
	
	class AffineTransformInfoMetadata: public :ref:`dlstreamer::DictionaryProxy<doxid-classdlstreamer_1_1_dictionary_proxy>` {
	public:
		// structs
	
		struct :ref:`key<doxid-structdlstreamer_1_1_affine_transform_info_metadata_1_1key>`;

		// fields
	
		static constexpr auto :target:`name<doxid-classdlstreamer_1_1_affine_transform_info_metadata_1a73b2c6dc63c35d6f104339eaaa32bcef>` = "AffineTransformMetadata";

		// methods
	
		std::vector<double> :target:`matrix<doxid-classdlstreamer_1_1_affine_transform_info_metadata_1a9c71863f2321c2564eb12ca99c486cf8>`() const;
		void :target:`set_matrix<doxid-classdlstreamer_1_1_affine_transform_info_metadata_1ae5fe04dbece56e4613349cdc507e00ad>`(const std::vector<double>& matrix);
	
		template <class RECT>
		void :target:`set_rect<doxid-classdlstreamer_1_1_affine_transform_info_metadata_1a130c44d87d14eee5f54a8162ec1b824b>`(
			double src_w,
			double src_h,
			double dst_w,
			double dst_h,
			const RECT& src_rect,
			const RECT& dst_rect
		);
	
		:target:`DictionaryProxy<doxid-classdlstreamer_1_1_affine_transform_info_metadata_1ae158807e1849bb907b83e364f985534d>`(:ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` dict);
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		virtual std::string :ref:`name<doxid-classdlstreamer_1_1_dictionary_1a0b3ae50e8e01b3e63aebc5ae55735931>`() const = 0;
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_dictionary_1a3bf8b56e3372c43db14063c1d0fa783c>`() const = 0;
		virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :ref:`try_get<doxid-classdlstreamer_1_1_dictionary_1a91ef8bc0807e8f27a4cd08eac5e073ae>`(std::string_view key) const = 0;
		virtual std::pair<const void*, size_t> :ref:`try_get_array<doxid-classdlstreamer_1_1_dictionary_1a8038122a2247af7d49c0538983fb4587>`(std::string_view key) const = 0;
		virtual void :ref:`set<doxid-classdlstreamer_1_1_dictionary_1a07d06ea3a8f9905f2db71171792608a3>`(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value) = 0;
		virtual void :ref:`set_array<doxid-classdlstreamer_1_1_dictionary_1ac2cea5376a4fa4033d1e606b619c3176>`(std::string_view key, const void* data, size_t nbytes) = 0;
		virtual void :ref:`set_name<doxid-classdlstreamer_1_1_dictionary_1a53e8ef5840d033ad145f2955f8cf181d>`(std::string const& name) = 0;
	
		template <typename T>
		T :ref:`get<doxid-classdlstreamer_1_1_dictionary_1a1d6204f7da82bed3fe5762f3f52513bb>`(std::string_view key) const;
	
		template <typename T>
		T :ref:`get<doxid-classdlstreamer_1_1_dictionary_1a96b9134b9349c562f9a25a6065a03676>`(std::string_view key, T default_value) const;
	
		template <class T>
		const std::vector<T> :ref:`get_array<doxid-classdlstreamer_1_1_dictionary_1a2552c3e81c18df3561e82de0b51ac353>`(std::string_view key) const;
	
		virtual std::string :ref:`name<doxid-classdlstreamer_1_1_dictionary_proxy_1a670a72a7d0512af14ee10d60dbe3990c>`() const;
		virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :ref:`try_get<doxid-classdlstreamer_1_1_dictionary_proxy_1ab375d4cbf3454fbf1b539427cbc268ee>`(std::string_view key) const;
		virtual std::pair<const void*, size_t> :ref:`try_get_array<doxid-classdlstreamer_1_1_dictionary_proxy_1a897fcbf39ec1defe3c7de223ca134651>`(std::string_view key) const;
		virtual void :ref:`set<doxid-classdlstreamer_1_1_dictionary_proxy_1adc60ae59b4a7bf180b5ac5db1436b8c2>`(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value);
		virtual void :ref:`set_array<doxid-classdlstreamer_1_1_dictionary_proxy_1a4cac5b25e3649aff74ad7cfc5cb088c1>`(std::string_view key, const void* data, size_t nbytes);
		virtual void :ref:`set_name<doxid-classdlstreamer_1_1_dictionary_proxy_1ac017bbf1843ea5f0dcec9b92d7534163>`(std::string const& name);
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_dictionary_proxy_1a3e9f02c866a60314b76d664b2c687982>`() const;

