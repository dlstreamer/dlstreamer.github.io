.. index:: pair: class; dlstreamer::Frame
.. _doxid-classdlstreamer_1_1_frame:

class dlstreamer::Frame
=======================

.. toctree::
	:hidden:

Overview
~~~~~~~~

:ref:`Frame <doxid-classdlstreamer_1_1_frame>` is collection of one or multiple :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` objects, attributes (media type and format), and optional metadata as container of :ref:`Dictionary <doxid-classdlstreamer_1_1_dictionary>` objects. :ref:`More...<details-classdlstreamer_1_1_frame>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <frame.h>
	
	class Frame {
	public:
		// typedefs
	
		typedef std::vector<:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>`>:::ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>`;

		// construction
	
		:target:`Frame<doxid-classdlstreamer_1_1_frame_1a7bfa6609b221e431df1c06aa73b9b614>`();
		:target:`Frame<doxid-classdlstreamer_1_1_frame_1a13fa72ec77948b0b2598597e7534b2d0>`(const Frame&);

		// methods
	
		Frame& :target:`operator =<doxid-classdlstreamer_1_1_frame_1a2249d111d9b0d255678c9116cdf922d2>` (const Frame&);
		virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` :ref:`media_type<doxid-classdlstreamer_1_1_frame_1aa861ea4b8c779aafa97b132f117e5991>`() const = 0;
		virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` :ref:`format<doxid-classdlstreamer_1_1_frame_1afdd9a118e7ce3dbcaed67e7ff5adb790>`() const = 0;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_frame_1ac4efd3522deaa0ed14741b3b3b0d1b48>`() const = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`begin<doxid-classdlstreamer_1_1_frame_1ac8829e750d05a18c9043767f39aa53ad>`() = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`end<doxid-classdlstreamer_1_1_frame_1a5f1252bb591a7b41b9314e82115a6762>`() = 0;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`tensor<doxid-classdlstreamer_1_1_frame_1aba0d6cbf42775dece521b06807b3b95c>`(int index = -1) = 0;
		virtual size_t :ref:`num_tensors<doxid-classdlstreamer_1_1_frame_1a066e3316f87dd4198224ce4394617a25>`() const = 0;
		virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_frame_1a3d2c7012a332e1a3b82873b449085009>`() = 0;
		const :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& :ref:`metadata<doxid-classdlstreamer_1_1_frame_1a98b1b2f5a9dd71a6c79e75828c8d0236>`() const;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`parent<doxid-classdlstreamer_1_1_frame_1a17a14802e030fbd46d05442d7c99019a>`() const = 0;
		virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> :ref:`regions<doxid-classdlstreamer_1_1_frame_1a2eb63ce1e72b522104c20609bddb1a69>`() const = 0;
	};

	// direct descendants

	class :ref:`BaseFrame<doxid-classdlstreamer_1_1_base_frame>`;
.. _details-classdlstreamer_1_1_frame:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

:ref:`Frame <doxid-classdlstreamer_1_1_frame>` is collection of one or multiple :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` objects, attributes (media type and format), and optional metadata as container of :ref:`Dictionary <doxid-classdlstreamer_1_1_dictionary>` objects.

Methods
-------

.. index:: pair: function; media_type
.. _doxid-classdlstreamer_1_1_frame_1aa861ea4b8c779aafa97b132f117e5991:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type() const = 0

Returns media type (Tensors, Image, Audio, etc).

.. index:: pair: function; format
.. _doxid-classdlstreamer_1_1_frame_1afdd9a118e7ce3dbcaed67e7ff5adb790:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` format() const = 0

Returns format (media type specific) of frame's data.

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_frame_1ac4efd3522deaa0ed14741b3b3b0d1b48:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const = 0

Returns memory type used for tensors allocation.

.. index:: pair: function; tensor
.. _doxid-classdlstreamer_1_1_frame_1aba0d6cbf42775dece521b06807b3b95c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` tensor(int index = -1) = 0

Returns tensor by index. If index less than 0 (default is -1), function checks that frame contains only one tensor and returns it, otherwise exception is thrown.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- index

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` index

.. index:: pair: function; num_tensors
.. _doxid-classdlstreamer_1_1_frame_1a066e3316f87dd4198224ce4394617a25:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual size_t num_tensors() const = 0

Returns number tensors in frame.

.. index:: pair: function; metadata
.. _doxid-classdlstreamer_1_1_frame_1a3d2c7012a332e1a3b82873b449085009:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& metadata() = 0

Returns metadata object.

.. index:: pair: function; metadata
.. _doxid-classdlstreamer_1_1_frame_1a98b1b2f5a9dd71a6c79e75828c8d0236:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`& metadata() const

Returns metadata object.

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_frame_1a17a14802e030fbd46d05442d7c99019a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` parent() const = 0

Returns parent frame if this frame was mapped (using :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>`) from another frame or contains sub-region of another frame, otherwise returns nullptr.

.. index:: pair: function; regions
.. _doxid-classdlstreamer_1_1_frame_1a2eb63ce1e72b522104c20609bddb1a69:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::vector<:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`> regions() const = 0

Returns list of regions. Each region typically represents an object detected on frame and may contain own metadata describing region specific attributes.

