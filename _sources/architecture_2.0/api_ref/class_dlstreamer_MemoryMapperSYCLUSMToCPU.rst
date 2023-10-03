.. index:: pair: class; dlstreamer::MemoryMapperSYCLUSMToCPU
.. _doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u:

class dlstreamer::MemoryMapperSYCLUSMToCPU
==========================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <sycl_usm_to_cpu.h>
	
	class MemoryMapperSYCLUSMToCPU: public :ref:`dlstreamer::BaseMemoryMapper<doxid-classdlstreamer_1_1_base_memory_mapper>` {
	public:
		// methods
	
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u_1ae77b397bb57bbe9739d9866d2b86e726>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
	
		:target:`BaseMemoryMapper<doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u_1a77d79fd0e116dfb03beed2bcdbf60830>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		);
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
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1afa920240e26d47be49df0699c025f27b>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a980282107d90d646919c9f2abcb98171>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_base_memory_mapper_1a32b70da011a63fdcde2c64e06867b377>`() const;
		:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);
		:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a5048502866215a573a0c23817061919e>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);

.. _details-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u_1ae77b397bb57bbe9739d9866d2b86e726:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` map(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode)

Map tensor into another context. The function returns mapped tensor, so that the parent() on output tensor returns original tensor and context() on output tensor returns :ref:`input_context() <doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>` to map

	*
		- mode

		- Access mode - read or write or read+write

