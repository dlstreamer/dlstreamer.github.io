.. index:: pair: class; dlstreamer::BaseSink
.. _doxid-classdlstreamer_1_1_base_sink:

class dlstreamer::BaseSink
==========================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <sink.h>
	
	class BaseSink: public :ref:`dlstreamer::BaseElement<doxid-classdlstreamer_1_1_base_element>` {
	public:
		// construction
	
		:target:`BaseSink<doxid-classdlstreamer_1_1_base_sink_1a1e48088be0934993b7161c8e48db5eae>`(const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context);

		// methods
	
		virtual void :ref:`set_input_info<doxid-classdlstreamer_1_1_base_sink_1a55f926319cdfe695f70cc83494799a9c>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
		virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :ref:`get_input_info<doxid-classdlstreamer_1_1_base_sink_1adfa56492a61bd9c191b1ec89292443e3>`();
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		bool :ref:`init<doxid-classdlstreamer_1_1_base_element_1a71225d2750ff83e2f568846affa17b76>`();
		:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_base_element_1aed010476c86c9db2f4814416477c6432>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`);

.. _details-classdlstreamer_1_1_base_sink:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; set_input_info
.. _doxid-classdlstreamer_1_1_base_sink_1a55f926319cdfe695f70cc83494799a9c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_input_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info)

The function notifies element about input information.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; get_input_info
.. _doxid-classdlstreamer_1_1_base_sink_1adfa56492a61bd9c191b1ec89292443e3:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` get_input_info()

Returns input information.

