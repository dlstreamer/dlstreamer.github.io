.. index:: pair: class; dlstreamer::Pool
.. _doxid-classdlstreamer_1_1_pool:

template class dlstreamer::Pool
===============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <pool.h>
	
	template <typename T>
	class Pool {
	public:
		// construction
	
		:target:`Pool<doxid-classdlstreamer_1_1_pool_1a87f61c36d2eb175f5d6257cf6a7c8ade>`(
			std::function<T()> allocator,
			std::function<bool(T&)> is_available,
			size_t max_pool_size = 0
		);

		// methods
	
		T :target:`get_or_create<doxid-classdlstreamer_1_1_pool_1afad57716e5e45bba5508441ca63ba888>`();
		size_t :target:`size<doxid-classdlstreamer_1_1_pool_1ac7067b6520b7e46b5f8365c445c170dd>`() const;
	};
