.. index:: pair: class; dlstreamer::BaseSource
.. _doxid-classdlstreamer_1_1_base_source:

class dlstreamer::BaseSource
============================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <source.h>
	
	class BaseSource: public :ref:`dlstreamer::BaseElement<doxid-classdlstreamer_1_1_base_element>` {
	public:
		// construction
	
		:target:`BaseSource<doxid-classdlstreamer_1_1_base_source_1a9ae6ee1c208f4240bbf3551f9162690e>`(const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context);

		// methods
	
		virtual void :ref:`set_output_info<doxid-classdlstreamer_1_1_base_source_1a1052b9c4b180d46833e40f39c780789f>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
		virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :ref:`get_output_info<doxid-classdlstreamer_1_1_base_source_1ab3eb968c3bb2167c52dda3b838eb6aac>`();
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		bool :ref:`init<doxid-classdlstreamer_1_1_base_element_1a71225d2750ff83e2f568846affa17b76>`();
		:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_base_element_1aed010476c86c9db2f4814416477c6432>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`);

.. _details-classdlstreamer_1_1_base_source:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; set_output_info
.. _doxid-classdlstreamer_1_1_base_source_1a1052b9c4b180d46833e40f39c780789f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_output_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info)

Enables post-processing (ex, resize, color-conversion) to specified format and tensor shape.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; get_output_info
.. _doxid-classdlstreamer_1_1_base_source_1ab3eb968c3bb2167c52dda3b838eb6aac:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` get_output_info()

Returns output information of the source.

