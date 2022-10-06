.. index:: pair: class; dlstreamer::TransformInplace
.. _doxid-classdlstreamer_1_1_transform_inplace:

class dlstreamer::TransformInplace
==================================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Abstract interface for in-place transform elements. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element doesn't allocate new frames/tensors, it modified input frames/tensors. :ref:`More...<details-classdlstreamer_1_1_transform_inplace>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <transform.h>
	
	class TransformInplace: public :ref:`dlstreamer::Element<doxid-classdlstreamer_1_1_element>` {
	public:
		// methods
	
		virtual void :ref:`set_info<doxid-classdlstreamer_1_1_transform_inplace_1a20f0f52628713390ded069adc42ee410>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0;
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_transform_inplace_1ae8be5250f2bd6a9e5ec572acc719c93e>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src) = 0;
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_transform_inplace_1a9b69fced73e7805b8a62bc2526b9fc2e>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src) = 0;
	};

	// direct descendants

	template <class T>
	class :ref:`BaseElement<doxid-classdlstreamer_1_1_base_element>`;

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		virtual bool :ref:`init<doxid-classdlstreamer_1_1_element_1ae3c10fbab46b7f5cce7054fdec95b89f>`() = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_element_1a64ab5ab3ed4c77ebce22d3874525783a>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0;

.. _details-classdlstreamer_1_1_transform_inplace:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Abstract interface for in-place transform elements. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element doesn't allocate new frames/tensors, it modified input frames/tensors.

Methods
-------

.. index:: pair: function; set_info
.. _doxid-classdlstreamer_1_1_transform_inplace_1a20f0f52628713390ded069adc42ee410:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0

The function notifies element about frame information.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>` information

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_inplace_1ae8be5250f2bd6a9e5ec572acc719c93e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src) = 0

Process tensor.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>`

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_inplace_1a9b69fced73e7805b8a62bc2526b9fc2e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src) = 0

Process frame.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>`

