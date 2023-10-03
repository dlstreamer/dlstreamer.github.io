.. index:: pair: struct; dlstreamer::FrameInfo
.. _doxid-structdlstreamer_1_1_frame_info:

struct dlstreamer::FrameInfo
============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <frame_info.h>
	
	struct FrameInfo {
		// fields
	
		:ref:`TensorInfoVector<doxid-namespacedlstreamer_1a6dc9660eef60412db1ceb13fc012734b>` :target:`tensors<doxid-structdlstreamer_1_1_frame_info_1af44c211d3c1246b5a497504eaf97a26a>`;
		:ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` :target:`media_type<doxid-structdlstreamer_1_1_frame_info_1a44ed9d8b7cc72c0dfcd97341f92978c8>`;
		:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :target:`memory_type<doxid-structdlstreamer_1_1_frame_info_1a8996478a033905c5cd862a1b6f8330a1>`;
		:ref:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>` :target:`format<doxid-structdlstreamer_1_1_frame_info_1af34dee3072196ec83048f1fdf609ea3e>`;

		// construction
	
		:target:`FrameInfo<doxid-structdlstreamer_1_1_frame_info_1ac3ab6138f4d762864d44adeac84ce2a6>`();
	
		:target:`FrameInfo<doxid-structdlstreamer_1_1_frame_info_1a9440b540fc27e3eca6dba457bff64612>`(
			:ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type,
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type = :ref:`MemoryType::Any<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dbaed36a1ef76a59ee3f15180e0441188ad>`,
			:ref:`TensorInfoVector<doxid-namespacedlstreamer_1a6dc9660eef60412db1ceb13fc012734b>` tensors = {}
		);
	
		:target:`FrameInfo<doxid-structdlstreamer_1_1_frame_info_1a96a3b645bd289a70eacc5ac62250540f>`(
			:ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` image_format,
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type = :ref:`MemoryType::CPU<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1dba2b55387dd066c5bac646ac61543d152d>`,
			:ref:`TensorInfoVector<doxid-namespacedlstreamer_1a6dc9660eef60412db1ceb13fc012734b>` tensors = {}
		);

		// methods
	
		bool :target:`operator <<doxid-structdlstreamer_1_1_frame_info_1abb2309e58ee38595ba7c9a0332aae7fe>` (const FrameInfo& r) const;
		bool :target:`operator ==<doxid-structdlstreamer_1_1_frame_info_1ac73d366d9d83244cdc1161375c88a7d0>` (const FrameInfo& r) const;
		bool :target:`operator !=<doxid-structdlstreamer_1_1_frame_info_1ab1cbbf96e32266d81e176e5c56a9c2b1>` (const FrameInfo& r) const;
	};
