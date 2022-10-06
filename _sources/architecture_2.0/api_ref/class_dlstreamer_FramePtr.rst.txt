.. index:: pair: class; dlstreamer::FramePtr
.. _doxid-classdlstreamer_1_1_frame_ptr:

class dlstreamer::FramePtr
==========================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <frame.h>
	
	class FramePtr: public std::shared_ptr< Frame > {
	public:
		// methods
	
		FramePtr :target:`map<doxid-classdlstreamer_1_1_frame_ptr_1a8d0e6fca0b00fcfc0489b7036dce90e8>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context,
			:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`
		);
	
		FramePtr :target:`map<doxid-classdlstreamer_1_1_frame_ptr_1a86e6f54564ccd13ab666710b3fe9f32e>`(:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`);
	
		template <typename T>
		std::shared_ptr<T> :target:`map<doxid-classdlstreamer_1_1_frame_ptr_1a75b6b67ad075f01e0433051aa3b46319>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context,
			:ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` access_mode = :ref:`AccessMode::ReadWrite<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10a70a2a84088d405a2e3f1e3accaa16723>`
		);
	
		:ref:`Frame::iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`begin<doxid-classdlstreamer_1_1_frame_ptr_1a42c086b768da7a981c952910722196e0>`();
		:ref:`Frame::iterator<doxid-classdlstreamer_1_1_frame_1aa6bd11d9daa1855e0bb0c0c2179ad529>` :target:`end<doxid-classdlstreamer_1_1_frame_ptr_1a6428f3d8c56c07f52ba406ed0122cb9e>`();
	};
