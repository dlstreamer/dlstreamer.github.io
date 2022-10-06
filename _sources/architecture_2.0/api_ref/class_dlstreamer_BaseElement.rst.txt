.. index:: pair: class; dlstreamer::BaseElement
.. _doxid-classdlstreamer_1_1_base_element:

template class dlstreamer::BaseElement
======================================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <element.h>
	
	template <class T>
	class BaseElement: public T {
	public:
		// methods
	
		bool :target:`init<doxid-classdlstreamer_1_1_base_element_1a71225d2750ff83e2f568846affa17b76>`();
		:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :target:`get_context<doxid-classdlstreamer_1_1_base_element_1aed010476c86c9db2f4814416477c6432>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`);
	};

	// direct descendants

	class :ref:`BaseSink<doxid-classdlstreamer_1_1_base_sink>`;
	class :ref:`BaseSource<doxid-classdlstreamer_1_1_base_source>`;
	class :ref:`BaseTransform<doxid-classdlstreamer_1_1_base_transform>`;
	class :ref:`BaseTransformInplace<doxid-classdlstreamer_1_1_base_transform_inplace>`;
