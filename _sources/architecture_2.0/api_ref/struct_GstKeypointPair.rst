.. index:: pair: struct; GstKeypointPair
.. _doxid-struct_gst_keypoint_pair:

struct GstKeypointPair
======================

.. toctree::
	:hidden:

:ref:`GstKeypointPair <doxid-struct_gst_keypoint_pair>` : @kp1: index of the first keypoint in a skeleton link. @kp2: index of the second keypoint in a skeleton link.

A pair of keypoints linked in a skeleton.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gstanalyticskeypointsmtd.h>
	
	struct GstKeypointPair {
		// fields
	
		guint :target:`kp1<doxid-struct_gst_keypoint_pair_1ada1c59e16e3c98254a04e64ed879984a>`;
		guint :target:`kp2<doxid-struct_gst_keypoint_pair_1a80b96daac2f8caa6b24bd4920ed60a66>`;
	};
