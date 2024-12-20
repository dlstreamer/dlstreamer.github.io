.. index:: pair: struct; GstAnalyticsKeypoint
.. _doxid-struct_gst_analytics_keypoint:

struct GstAnalyticsKeypoint
===========================

.. toctree::
	:hidden:

:ref:`GstAnalyticsKeypoint <doxid-struct_gst_analytics_keypoint>` : @x: zero-based absolute x pixel coordinate of a keypoint relative to image upper-left corner. @y: zero-based absolute y pixel coordinate of a keypoint relative to image upper-left corner. @z: normalized depth coordinate of a keypoint, relative to keypoint group center (use 0.0f for 2D keypoints). @v: visibility of a kepoint, normalized <0.0f - not visible, 1.0f - fully visible>.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gstanalyticskeypointsmtd.h>
	
	struct GstAnalyticsKeypoint {
		// fields
	
		guint :target:`x<doxid-struct_gst_analytics_keypoint_1a7ff7f1ec921579ebe4b23a39da022312>`;
		guint :target:`y<doxid-struct_gst_analytics_keypoint_1a2ddf21d31e0a4f9f194f86cd93396d1b>`;
		gfloat :target:`z<doxid-struct_gst_analytics_keypoint_1a9cbd2c8dcd74c74b34f7e722050086a9>`;
		gfloat :target:`v<doxid-struct_gst_analytics_keypoint_1aa402fb175c3276907335c9acde410cd3>`;
	};
