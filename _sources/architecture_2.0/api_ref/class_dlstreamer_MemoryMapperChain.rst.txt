.. index:: pair: class; dlstreamer::MemoryMapperChain
.. _doxid-classdlstreamer_1_1_memory_mapper_chain:

class dlstreamer::MemoryMapperChain
===================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <memory_mapper_factory.h>
	
	class MemoryMapperChain: public :ref:`dlstreamer::MemoryMapper<doxid-classdlstreamer_1_1_memory_mapper>` {
	public:
		// construction
	
		:target:`MemoryMapperChain<doxid-classdlstreamer_1_1_memory_mapper_chain_1a1b92c94ea3661cf78abb6f1d66903528>`(std::initializer_list<:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>`> l);
		:target:`MemoryMapperChain<doxid-classdlstreamer_1_1_memory_mapper_chain_1afb3b7169c6f07eda646db3d67abd8f72>`(const std::vector<:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>`>& v);

		// methods
	
		virtual :ref:`dlstreamer::TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_chain_1acd7c2e1ca5ff6e5b29151c9cce729f80>`(
			:ref:`dlstreamer::TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src,
			:ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode
		);
	
		virtual :ref:`dlstreamer::FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_chain_1a04bc63ab06f564233bb792f8f6c3bcce>`(
			:ref:`dlstreamer::FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src,
			:ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode
		);
	
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_memory_mapper_chain_1a25f6e78dfb74ab3a2f7a075927211bc8>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_memory_mapper_chain_1a090d3ec958fc083393844a87695af1ca>`() const;
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_1a5048502866215a573a0c23817061919e>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_memory_mapper_1a8d8493104cbd34a2195461bbe31e3aa5>`() const = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_memory_mapper_1a3404a1da382294265dad7d4f031ef157>`() const = 0;

.. _details-classdlstreamer_1_1_memory_mapper_chain:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_memory_mapper_chain_1acd7c2e1ca5ff6e5b29151c9cce729f80:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`dlstreamer::TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` map(
		:ref:`dlstreamer::TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src,
		:ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode
	)

Map tensor into another context. The function returns mapped tensor, so that the parent() on output tensor returns original tensor and context() on output tensor returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_chain_1a25f6e78dfb74ab3a2f7a075927211bc8>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` to map

	*
		- mode

		- Access mode - read or write or read+write

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_memory_mapper_chain_1a04bc63ab06f564233bb792f8f6c3bcce:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`dlstreamer::FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` map(
		:ref:`dlstreamer::FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src,
		:ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode
	)

Map frame into another context. The function returns mapped frame, so that the parent() on output frame returns original frame and context() on output frame returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_chain_1a25f6e78dfb74ab3a2f7a075927211bc8>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>` to map

	*
		- mode

		- Access mode - read or write or read+write

.. index:: pair: function; input_context
.. _doxid-classdlstreamer_1_1_memory_mapper_chain_1a25f6e78dfb74ab3a2f7a075927211bc8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` input_context() const

Returns context specified as input context on mapper object creation.

.. index:: pair: function; output_context
.. _doxid-classdlstreamer_1_1_memory_mapper_chain_1a090d3ec958fc083393844a87695af1ca:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` output_context() const

Returns context specified as output context on mapper object creation.

