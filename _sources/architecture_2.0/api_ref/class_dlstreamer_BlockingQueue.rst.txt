.. index:: pair: class; dlstreamer::BlockingQueue
.. _doxid-classdlstreamer_1_1_blocking_queue:

template class dlstreamer::BlockingQueue
========================================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <blocking_queue.h>
	
	template <typename T>
	class BlockingQueue {
	public:
		// methods
	
		void :target:`push<doxid-classdlstreamer_1_1_blocking_queue_1a1b5807c86f15aca9019f651dead358dd>`(T const& value, size_t queue_limit = 0);
		T :target:`pop<doxid-classdlstreamer_1_1_blocking_queue_1a2562f21c8dca6f45f889d96aeb26d79b>`();
		void :target:`clear<doxid-classdlstreamer_1_1_blocking_queue_1a351037853fe1a48905994cad83adb3d7>`();
		size_t :target:`size<doxid-classdlstreamer_1_1_blocking_queue_1a6f98b906b89d9e355216a10df15481f8>`();
	};
