.. index:: pair: class; dlstreamer::BaseMemoryMapper
.. _doxid-classdlstreamer_1_1_base_memory_mapper:

class dlstreamer::BaseMemoryMapper
==================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <memory_mapper.h>
	
	class BaseMemoryMapper: public :ref:`dlstreamer::MemoryMapper<doxid-classdlstreamer_1_1_memory_mapper>` {
	public:
		// construction
	
		:target:`BaseMemoryMapper<doxid-classdlstreamer_1_1_base_memory_mapper_1a77d79fd0e116dfb03beed2bcdbf60830>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		);

		// methods
	
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1afa920240e26d47be49df0699c025f27b>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a980282107d90d646919c9f2abcb98171>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode);
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`input_context<doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb>`() const;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`output_context<doxid-classdlstreamer_1_1_base_memory_mapper_1a32b70da011a63fdcde2c64e06867b377>`() const;
		:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);
		:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`map<doxid-classdlstreamer_1_1_base_memory_mapper_1a5048502866215a573a0c23817061919e>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);
	};

	// direct descendants

	class :ref:`MemoryMapperAnyToGST<doxid-classdlstreamer_1_1_memory_mapper_any_to_g_s_t>`;
	class :ref:`MemoryMapperCPUToOpenCV<doxid-classdlstreamer_1_1_memory_mapper_c_p_u_to_open_c_v>`;
	class :ref:`MemoryMapperCPUToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_c_p_u_to_open_v_i_n_o>`;
	class :ref:`MemoryMapperDMAToOpenCL<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_open_c_l>`;
	class :ref:`MemoryMapperDMAToUSM<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_u_s_m>`;
	class :ref:`MemoryMapperDMAToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperFFMPEGToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_f_f_m_p_e_g_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperGSTToDMA<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_d_m_a>`;
	class :ref:`MemoryMapperGSTToOpenCL<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_open_c_l>`;
	class :ref:`MemoryMapperGSTToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperOpenCLToCPU<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_c_p_u>`;
	class :ref:`MemoryMapperOpenCLToDMA<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_d_m_a>`;
	class :ref:`MemoryMapperOpenCLToOpenCVUMat<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_open_c_v_u_mat>`;
	class :ref:`MemoryMapperOpenCLToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_open_v_i_n_o>`;
	class :ref:`MemoryMapperOpenVINOToCPU<doxid-classdlstreamer_1_1_memory_mapper_open_v_i_n_o_to_c_p_u>`;
	class :ref:`MemoryMapperSYCLUSMToCPU<doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u>`;
	class :ref:`MemoryMapperUSMToDMA<doxid-classdlstreamer_1_1_memory_mapper_u_s_m_to_d_m_a>`;
	class :ref:`MemoryMapperVAAPIToDMA<doxid-classdlstreamer_1_1_memory_mapper_v_a_a_p_i_to_d_m_a>`;
	class :ref:`MemoryMapperVAAPIToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_v_a_a_p_i_to_open_v_i_n_o>`;

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

.. _details-classdlstreamer_1_1_base_memory_mapper:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1afa920240e26d47be49df0699c025f27b:

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

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1a980282107d90d646919c9f2abcb98171:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` map(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode)

Map frame into another context. The function returns mapped frame, so that the parent() on output frame returns original frame and context() on output frame returns :ref:`input_context() <doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb>`.



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
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` input_context() const

Returns context specified as input context on mapper object creation.

.. index:: pair: function; output_context
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1a32b70da011a63fdcde2c64e06867b377:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` output_context() const

Returns context specified as output context on mapper object creation.

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1a21c7ff8dd99cda38d2b81e739f209e9d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` map(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`)

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

.. index:: pair: function; map
.. _doxid-classdlstreamer_1_1_base_memory_mapper_1a5048502866215a573a0c23817061919e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` map(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`)

Map frame into another context. The function returns mapped frame, so that the parent() on output frame returns original frame and context() on output frame returns :ref:`input_context() <doxid-classdlstreamer_1_1_base_memory_mapper_1ae933baf67de5c90f16aa7ce7594c18cb>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>` to map

	*
		- mode

		- Access mode - read or write or read+write

