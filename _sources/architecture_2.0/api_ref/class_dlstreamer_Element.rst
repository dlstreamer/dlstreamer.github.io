.. index:: pair: class; dlstreamer::Element
.. _doxid-classdlstreamer_1_1_element:

class dlstreamer::Element
=========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Base class for all elements (:ref:`Source <doxid-classdlstreamer_1_1_source>`, :ref:`Transform <doxid-classdlstreamer_1_1_transform>`, :ref:`TransformInplace <doxid-classdlstreamer_1_1_transform_inplace>` and :ref:`Sink <doxid-classdlstreamer_1_1_sink>`) :ref:`More...<details-classdlstreamer_1_1_element>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <element.h>
	
	class Element {
	public:
		// methods
	
		virtual bool :ref:`init<doxid-classdlstreamer_1_1_element_1ae3c10fbab46b7f5cce7054fdec95b89f>`() = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_element_1a64ab5ab3ed4c77ebce22d3874525783a>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0;
	};

	// direct descendants

	class :ref:`Sink<doxid-classdlstreamer_1_1_sink>`;
	class :ref:`Source<doxid-classdlstreamer_1_1_source>`;
	class :ref:`Transform<doxid-classdlstreamer_1_1_transform>`;
	class :ref:`TransformInplace<doxid-classdlstreamer_1_1_transform_inplace>`;
.. _details-classdlstreamer_1_1_element:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Base class for all elements (:ref:`Source <doxid-classdlstreamer_1_1_source>`, :ref:`Transform <doxid-classdlstreamer_1_1_transform>`, :ref:`TransformInplace <doxid-classdlstreamer_1_1_transform_inplace>` and :ref:`Sink <doxid-classdlstreamer_1_1_sink>`)

The caller is responsible for thread safety.

Methods
-------

.. index:: pair: function; init
.. _doxid-classdlstreamer_1_1_element_1ae3c10fbab46b7f5cce7054fdec95b89f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool init() = 0

Initialize element according to input/output information. Function returns false in initialization failed.

.. index:: pair: function; get_context
.. _doxid-classdlstreamer_1_1_element_1a64ab5ab3ed4c77ebce22d3874525783a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` get_context(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0

The function requests element to create context of specified memory type (or return existent one). If context can't be created, function returns nullptr.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- memory_type

		- Memory type of requested context

