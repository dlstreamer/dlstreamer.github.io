.. index:: pair: class; dlstreamer::CPUFrameAlloc
.. _doxid-classdlstreamer_1_1_c_p_u_frame_alloc:

class dlstreamer::CPUFrameAlloc
===============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <frame_alloc.h>
	
	class CPUFrameAlloc: public :ref:`dlstreamer::BaseFrame<doxid-classdlstreamer_1_1_base_frame>` {
	public:
		// construction
	
		:target:`CPUFrameAlloc<doxid-classdlstreamer_1_1_c_p_u_frame_alloc_1accd1b76015609ffe1abd4ac202f48fd8>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// typedefs
	
		typedef std::vector<:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>`>:::ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>`;

		// methods
	
		:ref:`Frame<doxid-classdlstreamer_1_1_frame>`& :ref:`operator =<doxid-classdlstreamer_1_1_frame_1a2249d111d9b0d255678c9116cdf922d2>` (const :ref:`Frame<doxid-classdlstreamer_1_1_frame>`&);
		virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` :ref:`media_type<doxid-classdlstreamer_1_1_frame_1aa861ea4b8c779aafa97b132f117e5991>`() const = 0;
		virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` :ref:`format<doxid-classdlstreamer_1_1_frame_1afdd9a118e7ce3dbcaed67e7ff5adb790>`() const = 0;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_frame_1ac4efd3522deaa0ed14741b3b3b0d1b48>`() const = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :ref:`begin<doxid-classdlstreamer_1_1_frame_1ac8829e750d05a18c9043767f39aa53ad>`() = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :ref:`end<doxid-classdlstreamer_1_1_frame_1a5f1252bb591a7b41b9314e82115a6762>`() = 0;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`tensor<doxid-classdlstreamer_1_1_frame_1aba0d6cbf42775dece521b06807b3b95c>`(int index = -1) = 0;
		virtual size_t :ref:`num_tensors<doxid-classdlstreamer_1_1_frame_1a066e3316f87dd4198224ce4394617a25>`() const = 0;
		virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_frame_1a3d2c7012a332e1a3b82873b449085009>`() = 0;
		const :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_frame_1a98b1b2f5a9dd71a6c79e75828c8d0236>`() const;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_frame_1a17a14802e030fbd46d05442d7c99019a>`() const = 0;
		virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> :ref:`regions<doxid-classdlstreamer_1_1_frame_1a2eb63ce1e72b522104c20609bddb1a69>`() const = 0;
		virtual size_t :ref:`num_tensors<doxid-classdlstreamer_1_1_base_frame_1a5ff97686962780fe1101b3e2592ff855>`() const;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`tensor<doxid-classdlstreamer_1_1_base_frame_1adbbe7585f77111e5d3c35d01f791b92b>`(int index);
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :ref:`begin<doxid-classdlstreamer_1_1_base_frame_1a43c0c019c9274d71c5cc987ba3f6fef9>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :ref:`end<doxid-classdlstreamer_1_1_base_frame_1a652abfaf58e88e3651f4fcc4fa4a99c5>`();
		virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` :ref:`media_type<doxid-classdlstreamer_1_1_base_frame_1a8266cdb5b35258bd407b854a922ac43b>`() const;
		virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` :ref:`format<doxid-classdlstreamer_1_1_base_frame_1adf7272e1274dea0dfa26646c2a9ca7a6>`() const;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_frame_1a9b8beb6421e86ce4da38a3d24c43f082>`() const;
		virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_base_frame_1aaf3bebd53d91e4f336d05f255bf3cd0c>`();
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_base_frame_1aa270d22c9e8687f301663b6e9e92969d>`() const;
		void :ref:`set_parent<doxid-classdlstreamer_1_1_base_frame_1a5ac64122d54cef1994ca56614739311f>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` parent);
		virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> :ref:`regions<doxid-classdlstreamer_1_1_base_frame_1a64286cac9dad84afd1e5be2560d07f9a>`() const;
		void :ref:`add_region<doxid-classdlstreamer_1_1_base_frame_1a0368f628cdf3f4a930be2517cdbf41b6>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` frame);

