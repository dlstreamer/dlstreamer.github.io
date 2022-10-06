.. index:: pair: class; dlstreamer::Sink
.. _doxid-classdlstreamer_1_1_sink:

class dlstreamer::Sink
======================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Abstract interface for sink elements. :ref:`Sink <doxid-classdlstreamer_1_1_sink>` element has one input and no output. :ref:`More...<details-classdlstreamer_1_1_sink>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <sink.h>
	
	class Sink: public :ref:`dlstreamer::Element<doxid-classdlstreamer_1_1_element>` {
	public:
		// methods
	
		virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :ref:`get_input_info<doxid-classdlstreamer_1_1_sink_1aa1c935494e91c654d3044a3f94a1f7ac>`() = 0;
		virtual void :ref:`set_input_info<doxid-classdlstreamer_1_1_sink_1ac7acbe0841466ed68d05ad70984a1117>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0;
		virtual void :ref:`write<doxid-classdlstreamer_1_1_sink_1a355e58600735974b4997aceec8246ef0>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` frame) = 0;
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

.. _details-classdlstreamer_1_1_sink:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Abstract interface for sink elements. :ref:`Sink <doxid-classdlstreamer_1_1_sink>` element has one input and no output.

Methods
-------

.. index:: pair: function; get_input_info
.. _doxid-classdlstreamer_1_1_sink_1aa1c935494e91c654d3044a3f94a1f7ac:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` get_input_info() = 0

Returns input information.

.. index:: pair: function; set_input_info
.. _doxid-classdlstreamer_1_1_sink_1ac7acbe0841466ed68d05ad70984a1117:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_input_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0

The function notifies element about input information.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; write
.. _doxid-classdlstreamer_1_1_sink_1a355e58600735974b4997aceec8246ef0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void write(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` frame) = 0

Write one frame.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- frame

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>` to write

