.. index:: pair: class; dlstreamer::MemoryMapper
.. _doxid-classdlstreamer_1_1_memory_mapper:

class dlstreamer::MemoryMapper
==============================

.. toctree::
	:hidden:

Overview
~~~~~~~~

:ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` objects can map :ref:`TensorPtr <doxid-classdlstreamer_1_1_tensor_ptr>` or :ref:`FramePtr <doxid-classdlstreamer_1_1_frame_ptr>` from one context to another context. It could be mapping between GPU memory and CPU memory, or GPU to GPU mapping between two different frameworks (for example, mapping from OpenCL to SYCL) assuming two contexts allocated on same GPU device. :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` objects are created by :ref:`Context::get_mapper <doxid-classdlstreamer_1_1_context_1a0985e3f26b899ef792886121da05592f>` function, or utility function create_mapper which is able to create :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` object as chain of multiple mappers, for example OpenCL to DPC++/SYCL mapper is internally chain of three mappers OpenCL -> DMA -> LevelZero -> SYCL. :ref:`More...<details-classdlstreamer_1_1_memory_mapper>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <memory_mapper.h>
	
	class MemoryMapper {
	public:
		// methods
	
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_1a5048502866215a573a0c23817061919e>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_memory_mapper_1a8d8493104cbd34a2195461bbe31e3aa5>`() const = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_memory_mapper_1a3404a1da382294265dad7d4f031ef157>`() const = 0;
	};

	// direct descendants

	class :ref:`BaseMemoryMapper<doxid-classdlstreamer_1_1_base_memory_mapper>`;
	class :ref:`MemoryMapperCache<doxid-classdlstreamer_1_1_memory_mapper_cache>`;
	class :ref:`MemoryMapperChain<doxid-classdlstreamer_1_1_memory_mapper_chain>`;
.. _details-classdlstreamer_1_1_memory_mapper:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

:ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` objects can map :ref:`TensorPtr <doxid-classdlstreamer_1_1_tensor_ptr>` or :ref:`FramePtr <doxid-classdlstreamer_1_1_frame_ptr>` from one context to another context. It could be mapping between GPU memory and CPU memory, or GPU to GPU mapping between two different frameworks (for example, mapping from OpenCL to SYCL) assuming two contexts allocated on same GPU device. :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` objects are created by :ref:`Context::get_mapper <doxid-classdlstreamer_1_1_context_1a0985e3f26b899ef792886121da05592f>` function, or utility function create_mapper which is able to create :ref:`MemoryMapper <doxid-classdlstreamer_1_1_memory_mapper>` object as chain of multiple mappers, for example OpenCL to DPC++/SYCL mapper is internally chain of three mappers OpenCL -> DMA -> LevelZero -> SYCL.

Methods
-------

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` map(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0

Map tensor into another context. The function returns mapped tensor, so that the parent() on output tensor returns original tensor and context() on output tensor returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_1a8d8493104cbd34a2195461bbe31e3aa5>`.



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
.. _doxid-classdlstreamer_1_1_memory_mapper_1a5048502866215a573a0c23817061919e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` map(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`) = 0

Map frame into another context. The function returns mapped frame, so that the parent() on output frame returns original frame and context() on output frame returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_1a8d8493104cbd34a2195461bbe31e3aa5>`.



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
.. _doxid-classdlstreamer_1_1_memory_mapper_1a8d8493104cbd34a2195461bbe31e3aa5:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` input_context() const = 0

Returns context specified as input context on mapper object creation.

.. index:: pair: function; output_context
.. _doxid-classdlstreamer_1_1_memory_mapper_1a3404a1da382294265dad7d4f031ef157:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` output_context() const = 0

Returns context specified as output context on mapper object creation.

