.. index:: pair: class; dlstreamer::Tensor
.. _doxid-classdlstreamer_1_1_tensor:

class dlstreamer::Tensor
========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

:ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` is a multidimensional array. Tensors are similar to NumPy arrays, with main difference that tensor may allocate memory on GPU. Classes inherited from Tensors implement interface function via underlying frameworks ( for example OpenCL, DPC++, OpenCV, etc) and provide access to framework specific memory objects (for example, cl_mem, USM pointers, cv::Mat, etc). :ref:`More...<details-classdlstreamer_1_1_tensor>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>
	
	class Tensor {
	public:
		// typedefs
	
		typedef intptr_t :target:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>`;

		// construction
	
		:target:`Tensor<doxid-classdlstreamer_1_1_tensor_1a6048e81030d398976c496a75659195d2>`();
		:target:`Tensor<doxid-classdlstreamer_1_1_tensor_1a9443914b13a503afb90c0f5a8f835b8c>`(const Tensor&);

		// methods
	
		Tensor& :target:`operator =<doxid-classdlstreamer_1_1_tensor_1a4b3b7cb20ca834f3606d1f670456e6b7>` (const Tensor&);
		virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& :ref:`info<doxid-classdlstreamer_1_1_tensor_1af42140df5f13e3140d26a296df6c366b>`() const = 0;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_tensor_1aa2a2f30be1ba3defc3c38672155629dc>`() const = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`context<doxid-classdlstreamer_1_1_tensor_1a75198360d97a3dabb910bd99335bba1b>`() const = 0;
		virtual void* :ref:`data<doxid-classdlstreamer_1_1_tensor_1abf264c2e1587490637838a81b4d548ff>`() const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_tensor_1a3c1f486bfcd9209e2f1ebe61977aa014>`(std::string_view key = {}) const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_tensor_1ac65b75b1c769acc334d2a71750212475>`(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const = 0;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_tensor_1a7a84e600eb24eae0541573cee7754f46>`() const = 0;
	
		template <typename T>
		T* :target:`data<doxid-classdlstreamer_1_1_tensor_1a8cb2b5faa7e7073b6aa4c080a43c1be2>`() const;
	
		template <typename T>
		T* :target:`data<doxid-classdlstreamer_1_1_tensor_1a0f8f076ce34e24a463e3ad1473d1c293>`(
			std::vector<size_t> offset,
			bool left_offset = true
		) const;
	};

	// direct descendants

	class :ref:`BaseTensor<doxid-classdlstreamer_1_1_base_tensor>`;
.. _details-classdlstreamer_1_1_tensor:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

:ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` is a multidimensional array. Tensors are similar to NumPy arrays, with main difference that tensor may allocate memory on GPU. Classes inherited from Tensors implement interface function via underlying frameworks ( for example OpenCL, DPC++, OpenCV, etc) and provide access to framework specific memory objects (for example, cl_mem, USM pointers, cv::Mat, etc).

Methods
-------

.. index:: pair: function; info
.. _doxid-classdlstreamer_1_1_tensor_1af42140df5f13e3140d26a296df6c366b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info() const = 0

Returns tensor information - data type, shape, stride.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_tensor_1aa2a2f30be1ba3defc3c38672155629dc:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const = 0

Returns tensor's memory type.

.. index:: pair: function; context
.. _doxid-classdlstreamer_1_1_tensor_1a75198360d97a3dabb910bd99335bba1b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context() const = 0

Returns context used to create tensor. The :ref:`context() <doxid-classdlstreamer_1_1_tensor_1a75198360d97a3dabb910bd99335bba1b>` -> :ref:`memory_type() <doxid-classdlstreamer_1_1_tensor_1aa2a2f30be1ba3defc3c38672155629dc>` returns same type as :ref:`memory_type() <doxid-classdlstreamer_1_1_tensor_1aa2a2f30be1ba3defc3c38672155629dc>`. Function may return nullptr if tensor created without context, for example CPU-memory tensor.

.. index:: pair: function; data
.. _doxid-classdlstreamer_1_1_tensor_1abf264c2e1587490637838a81b4d548ff:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void* data() const = 0

Returns pointer to tensor data. If underlying memory allocation relies on abstract memory handle (for example, cl_mem), this function returns nullptr.

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_tensor_1a3c1f486bfcd9209e2f1ebe61977aa014:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle(std::string_view key = {}) const = 0

Returns a handle by key. If empty key, returns default handle. If no handle with the specified key, exception is thrown.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_tensor_1ac65b75b1c769acc334d2a71750212475:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const = 0

Returns a handle by key. If empty key, returns default handle. If no handle with the specified key, return default value specified in function parameter.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

	*
		- default_value

		- default value

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_tensor_1a7a84e600eb24eae0541573cee7754f46:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` parent() const = 0

Returns parent tensor if this tensor was mapped (using :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>`) from another tensor or contains sub-region of another tensor, otherwise returns nullptr.

