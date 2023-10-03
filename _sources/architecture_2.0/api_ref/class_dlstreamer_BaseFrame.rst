.. index:: pair: class; dlstreamer::BaseFrame
.. _doxid-classdlstreamer_1_1_base_frame:

class dlstreamer::BaseFrame
===========================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <frame.h>
	
	class BaseFrame: public :ref:`dlstreamer::Frame<doxid-classdlstreamer_1_1_frame>` {
	public:
		// construction
	
		:target:`BaseFrame<doxid-classdlstreamer_1_1_base_frame_1ad46c85d211a7510011669334e65a2459>`(:ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type, :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` format, :ref:`TensorVector<doxid-namespacedlstreamer_1aef57279f206868573faca2d977200ea9>` tensors);
		:target:`BaseFrame<doxid-classdlstreamer_1_1_base_frame_1a60230e9eb6c23e050149da9ee05e208d>`(:ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type, :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` format, :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);

		// methods
	
		virtual size_t :ref:`num_tensors<doxid-classdlstreamer_1_1_base_frame_1a5ff97686962780fe1101b3e2592ff855>`() const;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`tensor<doxid-classdlstreamer_1_1_base_frame_1adbbe7585f77111e5d3c35d01f791b92b>`(int index);
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`begin<doxid-classdlstreamer_1_1_base_frame_1a43c0c019c9274d71c5cc987ba3f6fef9>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`end<doxid-classdlstreamer_1_1_base_frame_1a652abfaf58e88e3651f4fcc4fa4a99c5>`();
		virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` :ref:`media_type<doxid-classdlstreamer_1_1_base_frame_1a8266cdb5b35258bd407b854a922ac43b>`() const;
		virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` :ref:`format<doxid-classdlstreamer_1_1_base_frame_1adf7272e1274dea0dfa26646c2a9ca7a6>`() const;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_frame_1a9b8beb6421e86ce4da38a3d24c43f082>`() const;
		virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_base_frame_1aaf3bebd53d91e4f336d05f255bf3cd0c>`();
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_base_frame_1aa270d22c9e8687f301663b6e9e92969d>`() const;
		void :target:`set_parent<doxid-classdlstreamer_1_1_base_frame_1a5ac64122d54cef1994ca56614739311f>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` parent);
		virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> :ref:`regions<doxid-classdlstreamer_1_1_base_frame_1a64286cac9dad84afd1e5be2560d07f9a>`() const;
		void :target:`add_region<doxid-classdlstreamer_1_1_base_frame_1a0368f628cdf3f4a930be2517cdbf41b6>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` frame);
	};

	// direct descendants

	class :ref:`CPUFrameAlloc<doxid-classdlstreamer_1_1_c_p_u_frame_alloc>`;
	class :ref:`FFmpegFrame<doxid-classdlstreamer_1_1_f_fmpeg_frame>`;
	class :ref:`GSTFrame<doxid-classdlstreamer_1_1_g_s_t_frame>`;
	class :ref:`OpenVINOFrame<doxid-classdlstreamer_1_1_open_v_i_n_o_frame>`;
	class :ref:`VAAPIFrame<doxid-classdlstreamer_1_1_v_a_a_p_i_frame>`;

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

.. _details-classdlstreamer_1_1_base_frame:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; num_tensors
.. _doxid-classdlstreamer_1_1_base_frame_1a5ff97686962780fe1101b3e2592ff855:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual size_t num_tensors() const

Returns number tensors in frame.

.. index:: pair: function; tensor
.. _doxid-classdlstreamer_1_1_base_frame_1adbbe7585f77111e5d3c35d01f791b92b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` tensor(int index)

Returns tensor by index. If index less than 0 (default is -1), function checks that frame contains only one tensor and returns it, otherwise exception is thrown.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- index

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` index

.. index:: pair: function; media_type
.. _doxid-classdlstreamer_1_1_base_frame_1a8266cdb5b35258bd407b854a922ac43b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type() const

Returns media type (Tensors, Image, Audio, etc).

.. index:: pair: function; format
.. _doxid-classdlstreamer_1_1_base_frame_1adf7272e1274dea0dfa26646c2a9ca7a6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` format() const

Returns format (media type specific) of frame's data.

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_base_frame_1a9b8beb6421e86ce4da38a3d24c43f082:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const

Returns memory type used for tensors allocation.

.. index:: pair: function; metadata
.. _doxid-classdlstreamer_1_1_base_frame_1aaf3bebd53d91e4f336d05f255bf3cd0c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& metadata()

Returns metadata object.

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_base_frame_1aa270d22c9e8687f301663b6e9e92969d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` parent() const

Returns parent frame if this frame was mapped (using :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>`) from another frame or contains sub-region of another frame, otherwise returns nullptr.

.. index:: pair: function; regions
.. _doxid-classdlstreamer_1_1_base_frame_1a64286cac9dad84afd1e5be2560d07f9a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> regions() const

Returns list of regions. Each region typically represents an object detected on frame and may contain own metadata describing region specific attributes.

