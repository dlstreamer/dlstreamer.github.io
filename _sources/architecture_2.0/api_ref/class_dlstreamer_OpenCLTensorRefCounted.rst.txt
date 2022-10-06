.. index:: pair: class; dlstreamer::OpenCLTensorRefCounted
.. _doxid-classdlstreamer_1_1_open_c_l_tensor_ref_counted:

class dlstreamer::OpenCLTensorRefCounted
========================================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor_ref_counted.h>
	
	class OpenCLTensorRefCounted: public :ref:`dlstreamer::OpenCLTensor<doxid-classdlstreamer_1_1_open_c_l_tensor>` {
	public:
		// construction
	
		:target:`OpenCLTensorRefCounted<doxid-classdlstreamer_1_1_open_c_l_tensor_ref_counted_1af818d031084914628a371217a6f63bf2>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info, :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context, :ref:`cl_mem<doxid-opencl_2tensor_8h_1af2141916ad9655073b9810d7bc71494d>` mem);
		:target:`OpenCLTensorRefCounted<doxid-classdlstreamer_1_1_open_c_l_tensor_ref_counted_1a09f90902601389fcab4cb4b1416ef927>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info, :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` context);
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
		:ref:`cl_mem<doxid-opencl_2tensor_8h_1af2141916ad9655073b9810d7bc71494d>` :ref:`clmem<doxid-classdlstreamer_1_1_open_c_l_tensor_1a5bdbec35b284b324854cf1219c5be9d7>`() const;
		:ref:`operator cl_mem<doxid-classdlstreamer_1_1_open_c_l_tensor_1a7f3ccc5991a4e6b4a246a36d4b97a6c4>` () const;
		size_t :ref:`offset<doxid-classdlstreamer_1_1_open_c_l_tensor_1a53dc5ea4368f6f04c8a0516344f204c7>`() const;

