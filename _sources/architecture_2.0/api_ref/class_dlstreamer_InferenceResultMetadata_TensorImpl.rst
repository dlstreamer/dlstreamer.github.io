.. index:: pair: class; dlstreamer::InferenceResultMetadata::TensorImpl
.. _doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl:

class dlstreamer::InferenceResultMetadata::TensorImpl
=====================================================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	class TensorImpl: public :ref:`dlstreamer::Tensor<doxid-classdlstreamer_1_1_tensor>` {
	public:
		// construction
	
		:target:`TensorImpl<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1a7e8323701ce2ab1a806fec2552378d7f>`(void* data, const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info);

		// methods
	
		const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& :target:`info<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1a183f1b434955c98e1fafb82b246e655c>`() const;
		:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :target:`memory_type<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1a99ff4c8579056997987ae15732d4165c>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :target:`context<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1ad791ea353aabe623e6b8483e8c38bd00>`() const;
		void* :target:`data<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1a6ec39a549bcd4e902d2aabed4f09f587>`() const;
		:ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :target:`handle<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1a1e38ba80b74288312b4df8e8d67c518a>`(std::string_view) const;
		:ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :target:`handle<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1ad3553c52e4537620220b66d287fc9f8b>`(std::string_view, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>`) const;
		:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :target:`parent<doxid-classdlstreamer_1_1_inference_result_metadata_1_1_tensor_impl_1abe6443c9082152b4b72581ea22f98ac8>`() const;
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// typedefs
	
		typedef intptr_t :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>`;

		// methods
	
		:ref:`Tensor<doxid-classdlstreamer_1_1_tensor>`& :ref:`operator =<doxid-classdlstreamer_1_1_tensor_1a4b3b7cb20ca834f3606d1f670456e6b7>` (const :ref:`Tensor<doxid-classdlstreamer_1_1_tensor>`&);
		virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& :ref:`info<doxid-classdlstreamer_1_1_tensor_1af42140df5f13e3140d26a296df6c366b>`() const = 0;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_tensor_1aa2a2f30be1ba3defc3c38672155629dc>`() const = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`context<doxid-classdlstreamer_1_1_tensor_1a75198360d97a3dabb910bd99335bba1b>`() const = 0;
		virtual void* :ref:`data<doxid-classdlstreamer_1_1_tensor_1abf264c2e1587490637838a81b4d548ff>`() const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_tensor_1a3c1f486bfcd9209e2f1ebe61977aa014>`(std::string_view key = {}) const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_tensor_1ac65b75b1c769acc334d2a71750212475>`(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const = 0;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_tensor_1a7a84e600eb24eae0541573cee7754f46>`() const = 0;
	
		template <typename T>
		T* :ref:`data<doxid-classdlstreamer_1_1_tensor_1a8cb2b5faa7e7073b6aa4c080a43c1be2>`() const;
	
		template <typename T>
		T* :ref:`data<doxid-classdlstreamer_1_1_tensor_1a0f8f076ce34e24a463e3ad1473d1c293>`(
			std::vector<size_t> offset,
			bool left_offset = true
		) const;

