.. index:: pair: class; dlstreamer::Source
.. _doxid-classdlstreamer_1_1_source:

class dlstreamer::Source
========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Abstract interface for source elements. :ref:`Source <doxid-classdlstreamer_1_1_source>` element has one output and no input. :ref:`Source <doxid-classdlstreamer_1_1_source>` element is responsible for allocating output frame/tensor. :ref:`More...<details-classdlstreamer_1_1_source>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <source.h>
	
	class Source: public :ref:`dlstreamer::Element<doxid-classdlstreamer_1_1_element>` {
	public:
		// methods
	
		virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :ref:`get_output_info<doxid-classdlstreamer_1_1_source_1ae59aaf97ebe37e3243adeb572fb83461>`() = 0;
		virtual void :ref:`set_output_info<doxid-classdlstreamer_1_1_source_1ae1a6860a4ef4b5d2f5fc8c94f1356d10>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`read<doxid-classdlstreamer_1_1_source_1a1fad9ed93b85c6baa840a11931f9cbc6>`() = 0;
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

.. _details-classdlstreamer_1_1_source:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Abstract interface for source elements. :ref:`Source <doxid-classdlstreamer_1_1_source>` element has one output and no input. :ref:`Source <doxid-classdlstreamer_1_1_source>` element is responsible for allocating output frame/tensor.

Methods
-------

.. index:: pair: function; get_output_info
.. _doxid-classdlstreamer_1_1_source_1ae59aaf97ebe37e3243adeb572fb83461:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` get_output_info() = 0

Returns output information of the source.

.. index:: pair: function; set_output_info
.. _doxid-classdlstreamer_1_1_source_1ae1a6860a4ef4b5d2f5fc8c94f1356d10:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_output_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0

Enables post-processing (ex, resize, color-conversion) to specified format and tensor shape.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; read
.. _doxid-classdlstreamer_1_1_source_1a1fad9ed93b85c6baa840a11931f9cbc6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` read() = 0

Read one frame from the source.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- dst

		- Output frame

