.. index:: pair: struct; GstKeypoint
.. _doxid-struct_gst_keypoint:

struct GstKeypoint
==================

.. toctree::
	:hidden:

:ref:`GstKeypoint <doxid-struct_gst_keypoint>` : @x: absolute x coordinate of a keypoint in image domain. @y: absolute y coordinate of a keypoint in image domain. @z: (3D only, use 0.0f for 2D) normalized depth coordinate of a keypoint. @v: visibility of a kepoint, normalized <0.0f - not visible, 1.0f - fully visible>.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gstanalyticskeypointsmtd.h>
	
	struct GstKeypoint {
		// fields
	
		guint :target:`x<doxid-struct_gst_keypoint_1ae3e4b37e552f5952cc1fb824be80ab3c>`;
		guint :target:`y<doxid-struct_gst_keypoint_1a4534247b1d351a7cea3852e14d2e2b03>`;
		gfloat :target:`z<doxid-struct_gst_keypoint_1aa3372645f865c0ea4b037b6109b1600f>`;
		gfloat :target:`v<doxid-struct_gst_keypoint_1a57be7b5f575c0ab4670239ebf8052b96>`;
	};
