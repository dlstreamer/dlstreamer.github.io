.. index:: pair: class; dlstreamer::MemoryMapperCache
.. _doxid-classdlstreamer_1_1_memory_mapper_cache:

class dlstreamer::MemoryMapperCache
===================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <memory_mapper_factory.h>
	
	class MemoryMapperCache: public :ref:`dlstreamer::MemoryMapper<doxid-classdlstreamer_1_1_memory_mapper>` {
	public:
		// construction
	
		:target:`MemoryMapperCache<doxid-classdlstreamer_1_1_memory_mapper_cache_1ac5cfca6ff6de0fbd27e53a3cb08c2883>`(:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` mapper);

		// methods
	
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_cache_1ab70bf6d926ee9ad9b99578f88e840b46>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_cache_1a41c92078fe4bfb6c1b83200d8a119728>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_memory_mapper_cache_1a8428acd5d1ec505b2f31d42a31474849>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_memory_mapper_cache_1a256a31f9057454d823bf688aa6286e24>`() const;
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

.. _details-classdlstreamer_1_1_memory_mapper_cache:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_memory_mapper_cache_1ab70bf6d926ee9ad9b99578f88e840b46:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` map(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode)

Map tensor into another context. The function returns mapped tensor, so that the parent() on output tensor returns original tensor and context() on output tensor returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_cache_1a8428acd5d1ec505b2f31d42a31474849>`.



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
.. _doxid-classdlstreamer_1_1_memory_mapper_cache_1a41c92078fe4bfb6c1b83200d8a119728:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` map(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`dlstreamer::AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode)

Map frame into another context. The function returns mapped frame, so that the parent() on output frame returns original frame and context() on output frame returns :ref:`input_context() <doxid-classdlstreamer_1_1_memory_mapper_cache_1a8428acd5d1ec505b2f31d42a31474849>`.



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
.. _doxid-classdlstreamer_1_1_memory_mapper_cache_1a8428acd5d1ec505b2f31d42a31474849:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` input_context() const

Returns context specified as input context on mapper object creation.

.. index:: pair: function; output_context
.. _doxid-classdlstreamer_1_1_memory_mapper_cache_1a256a31f9057454d823bf688aa6286e24:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` output_context() const

Returns context specified as output context on mapper object creation.

