.. index:: pair: class; dlstreamer::BaseTensor
.. _doxid-classdlstreamer_1_1_base_tensor:

class dlstreamer::BaseTensor
============================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>
	
	class BaseTensor: public :ref:`dlstreamer::Tensor<doxid-classdlstreamer_1_1_tensor>` {
	public:
		// construction
	
		:target:`BaseTensor<doxid-classdlstreamer_1_1_base_tensor_1a1ec6ac066c367eb66e0d5f8a7a529957>`(
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type,
			const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info,
			std::string_view primary_key = {},
			:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context = nullptr
		);

		// methods
	
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_tensor_1ac2c3e5a0733d4f8620eb161e3986691d>`() const;
		virtual void* :ref:`data<doxid-classdlstreamer_1_1_base_tensor_1acaff7d97721e57df19ace11bf0488731>`() const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_base_tensor_1a9c986f6469deed26b6f95af3d69bb999>`(std::string_view key) const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_base_tensor_1a23db3f0ead8ce2aa7be2aed6f2847742>`(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const;
		virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& :ref:`info<doxid-classdlstreamer_1_1_base_tensor_1a5183ca81efaf28ca5a9881ac1e0355a1>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`context<doxid-classdlstreamer_1_1_base_tensor_1a70dc8241e41032be5ce3b17ff5a21a79>`() const;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_base_tensor_1a14d61d74ccc5705f90ac0cd8f83bf1ae>`() const;
		void :target:`set_parent<doxid-classdlstreamer_1_1_base_tensor_1af76812458db8e89cd691a26bcb302405>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` parent);
		void :target:`set_handle<doxid-classdlstreamer_1_1_base_tensor_1a4742500e0c6e7428626cfd147d94fbc9>`(const std::string& key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle);
	};

	// direct descendants

	class :ref:`CPUTensor<doxid-classdlstreamer_1_1_c_p_u_tensor>`;
	class :ref:`DMATensor<doxid-classdlstreamer_1_1_d_m_a_tensor>`;
	class :ref:`GSTTensor<doxid-classdlstreamer_1_1_g_s_t_tensor>`;
	class :ref:`OpenCLTensor<doxid-classdlstreamer_1_1_open_c_l_tensor>`;
	class :ref:`OpenCVTensor<doxid-classdlstreamer_1_1_open_c_v_tensor>`;
	class :ref:`OpenCVUMatTensor<doxid-classdlstreamer_1_1_open_c_v_u_mat_tensor>`;
	class :ref:`OpenVINOTensor<doxid-classdlstreamer_1_1_open_v_i_n_o_tensor>`;
	class :ref:`SYCLUSMTensor<doxid-classdlstreamer_1_1_s_y_c_l_u_s_m_tensor>`;
	class :ref:`USMTensor<doxid-classdlstreamer_1_1_u_s_m_tensor>`;
	class :ref:`VAAPITensor<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor>`;

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

.. _details-classdlstreamer_1_1_base_tensor:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_base_tensor_1ac2c3e5a0733d4f8620eb161e3986691d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const

Returns tensor's memory type.

.. index:: pair: function; data
.. _doxid-classdlstreamer_1_1_base_tensor_1acaff7d97721e57df19ace11bf0488731:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void* data() const

Returns pointer to tensor data. If underlying memory allocation relies on abstract memory handle (for example, cl_mem), this function returns nullptr.

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_base_tensor_1a9c986f6469deed26b6f95af3d69bb999:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle(std::string_view key) const

Returns a handle by key. If empty key, returns default handle. If no handle with the specified key, exception is thrown.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_base_tensor_1a23db3f0ead8ce2aa7be2aed6f2847742:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const

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

.. index:: pair: function; info
.. _doxid-classdlstreamer_1_1_base_tensor_1a5183ca81efaf28ca5a9881ac1e0355a1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info() const

Returns tensor information - data type, shape, stride.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; context
.. _doxid-classdlstreamer_1_1_base_tensor_1a70dc8241e41032be5ce3b17ff5a21a79:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context() const

Returns context used to create tensor. The :ref:`context() <doxid-classdlstreamer_1_1_base_tensor_1a70dc8241e41032be5ce3b17ff5a21a79>` -> :ref:`memory_type() <doxid-classdlstreamer_1_1_base_tensor_1ac2c3e5a0733d4f8620eb161e3986691d>` returns same type as :ref:`memory_type() <doxid-classdlstreamer_1_1_base_tensor_1ac2c3e5a0733d4f8620eb161e3986691d>`. Function may return nullptr if tensor created without context, for example CPU-memory tensor.

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_base_tensor_1a14d61d74ccc5705f90ac0cd8f83bf1ae:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` parent() const

Returns parent tensor if this tensor was mapped (using :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>`) from another tensor or contains sub-region of another tensor, otherwise returns nullptr.

