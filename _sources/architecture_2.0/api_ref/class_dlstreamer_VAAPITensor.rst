.. index:: pair: class; dlstreamer::VAAPITensor
.. _doxid-classdlstreamer_1_1_v_a_a_p_i_tensor:

class dlstreamer::VAAPITensor
=============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>
	
	class VAAPITensor: public :ref:`dlstreamer::BaseTensor<doxid-classdlstreamer_1_1_base_tensor>` {
	public:
		// typedefs
	
		typedef uint32_t :target:`VASurfaceID<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a6d32fb46cdfeadee14101662fbb53118>`;

		// construction
	
		:target:`VAAPITensor<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a848c2cf731059deaa2157d71919b7055>`(
			:ref:`VASurfaceID<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a6d32fb46cdfeadee14101662fbb53118>` va_surface,
			int plane_index,
			const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info,
			:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context
		);

		// methods
	
		:ref:`VASurfaceID<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a6d32fb46cdfeadee14101662fbb53118>` :target:`va_surface<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a06e0e68e4c46a1f1cc92b54622968003>`();
		int :target:`plane_index<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1aae3466c3781f381a337b78978dc94de8>`();
		int :target:`offset_x<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a5e261fa4dd567597edcf97fe4a1a3249>`();
		int :target:`offset_y<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor_1a266daab4dc0fb85f4cbc1bb6626870de>`();
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
	
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_tensor_1ac2c3e5a0733d4f8620eb161e3986691d>`() const;
		virtual void* :ref:`data<doxid-classdlstreamer_1_1_base_tensor_1acaff7d97721e57df19ace11bf0488731>`() const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_base_tensor_1a9c986f6469deed26b6f95af3d69bb999>`(std::string_view key) const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` :ref:`handle<doxid-classdlstreamer_1_1_base_tensor_1a23db3f0ead8ce2aa7be2aed6f2847742>`(std::string_view key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` default_value) const;
		virtual const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& :ref:`info<doxid-classdlstreamer_1_1_base_tensor_1a5183ca81efaf28ca5a9881ac1e0355a1>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`context<doxid-classdlstreamer_1_1_base_tensor_1a70dc8241e41032be5ce3b17ff5a21a79>`() const;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_base_tensor_1a14d61d74ccc5705f90ac0cd8f83bf1ae>`() const;
		void :ref:`set_parent<doxid-classdlstreamer_1_1_base_tensor_1af76812458db8e89cd691a26bcb302405>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` parent);
		void :ref:`set_handle<doxid-classdlstreamer_1_1_base_tensor_1a4742500e0c6e7428626cfd147d94fbc9>`(const std::string& key, :ref:`handle_t<doxid-classdlstreamer_1_1_tensor_1a9331617dd714a28e9fbd33b4bc3b7a99>` handle);

