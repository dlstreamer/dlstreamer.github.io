.. index:: pair: namespace; dlstreamer::detail
.. _doxid-namespacedlstreamer_1_1detail:

namespace dlstreamer::detail
============================

.. toctree::
	:hidden:

	struct_dlstreamer_detail_fourcc.rst




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	namespace detail {

	// structs

	template <int a, int b, int c, int d>
	struct :ref:`fourcc<doxid-structdlstreamer_1_1detail_1_1fourcc>`;

	// global variables

	static std::string_view :target:`GST_VIDEO_MEDIA_NAME<doxid-namespacedlstreamer_1_1detail_1ab2f68f25dfd09c56dab22cb63bb2a46d>` = "video/x-raw";

	// global functions

	:ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`gst_video_caps_to_frame_info<doxid-namespacedlstreamer_1_1detail_1aa100a673f3fcb9b4ff4244aa12a3dbda>`(const GstCaps* caps, guint index);
	:ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`gst_tensor_caps_to_frame_info<doxid-namespacedlstreamer_1_1detail_1ad653da457fbb7e4d24db6ddcad387613>`(const GstCaps* caps, guint index);
	GstStructure* :target:`frame_info_to_gst_video_caps<doxid-namespacedlstreamer_1_1detail_1a23b41bb1750a195a7aa362aa9e4ef580>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
	GstStructure* :target:`frame_info_to_gst_tensor_caps<doxid-namespacedlstreamer_1_1detail_1a5158b33d6bda69394e497dde6f6be730>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);

	} // namespace detail
