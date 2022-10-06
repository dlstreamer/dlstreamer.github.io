.. index:: pair: class; dlstreamer::TensorPtr
.. _doxid-classdlstreamer_1_1_tensor_ptr:

class dlstreamer::TensorPtr
===========================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>
	
	class TensorPtr: public std::shared_ptr< Tensor > {
	public:
		// methods
	
		TensorPtr :target:`map<doxid-classdlstreamer_1_1_tensor_ptr_1a9c713230f6a7ffbdca803f6703d33dec>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context = nullptr,
			:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`
		);
	
		TensorPtr :target:`map<doxid-classdlstreamer_1_1_tensor_ptr_1ae443ac9701ea303df9406e4db978b65e>`(:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);
	
		template <typename T>
		std::shared_ptr<T> :target:`map<doxid-classdlstreamer_1_1_tensor_ptr_1a869adaa2e3a247b4889eb5ede877feec>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context,
			:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`
		);
	};
