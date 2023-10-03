.. index:: pair: struct; GVA::Segment
.. _doxid-struct_g_v_a_1_1_segment:

template struct GVA::Segment
============================

.. toctree::
	:hidden:

Template structure for audio segment containing start, end fields.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <audio_event.h>
	
	template <typename T>
	struct Segment {
		// fields
	
		T :target:`start<doxid-struct_g_v_a_1_1_segment_1acc9ddddfc32468c23fa3f698133aaa84>`;
		T :target:`end<doxid-struct_g_v_a_1_1_segment_1a49c40e01111cdc71bdfdaefa5ad7dc08>`;
	};
