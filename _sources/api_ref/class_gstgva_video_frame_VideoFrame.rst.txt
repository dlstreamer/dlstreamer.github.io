.. index:: pair: class; gstgva::video_frame::VideoFrame
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame:

class gstgva::video_frame::VideoFrame
=====================================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents video frame - object for working with RegionOfInterest and Tensor objects which belong to this video frame (image). :ref:`More...<details-classgstgva_1_1video__frame_1_1_video_frame>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	class VideoFrame {
	public:
		// methods
	
		def :ref:`__init__<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a6e80b69e5fc02be56888cc1f9defe1a9>`(
			self self,
			Gst.Buffer buffer,
			GstVideo.VideoInfo video_info = None,
			Gst.Caps caps = None
		);
	
		GstVideo.VideoMeta :ref:`video_meta<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a660a083a7c0827e3e05b837f3b19db56>`(self self);
		GstVideo.VideoInfo :ref:`video_info<doxid-classgstgva_1_1video__frame_1_1_video_frame_1ab20943e0804b2f72effefb587389877f>`(self self);
		def :ref:`regions<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a1e8dc83ad23ea3f503c6354abaf8fc53>`(self self);
		def :ref:`tensors<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a77d5b23d5e7b94b4c8ce376d05fb6f8d>`(self self);
	
		:ref:`RegionOfInterest<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` :ref:`add_region<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a91d71fb1082fb075250c8cc10bbed2c2>`(
			self self,
			x x,
			y y,
			w w,
			h h,
			str label = "",
			float confidence = 0.0,
			bool normalized = False
		);
	
		:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` :ref:`add_tensor<doxid-classgstgva_1_1video__frame_1_1_video_frame_1aad298cbe68a61de4de8906d68ec180c2>`(self self);
		List[str] :ref:`messages<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a160a71ad120bcec8bd79180c5b3eacfb>`(self self);
		def :ref:`add_message<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a2139fee1f13df31bf32a5fc4f04ac63d>`(self self, str message);
		def :ref:`remove_message<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a16155c418a3f52d137ad2851af529bd4>`(self self, str message);
		None :ref:`remove_region<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a2a0ddef58a7550cb5d9f83a5a9cb9e22>`(self self, roi roi);
		numpy.ndarray :ref:`data<doxid-classgstgva_1_1video__frame_1_1_video_frame_1a4efa6760f87f7a2fa6560a01089d5ed7>`(self self, Gst.MapFlags flag = Gst.MapFlags.READ);
	};
.. _details-classgstgva_1_1video__frame_1_1_video_frame:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents video frame - object for working with RegionOfInterest and Tensor objects which belong to this video frame (image).

RegionOfInterest describes detected object (bounding boxes) and its Tensor objects (inference results on RegionOfInterest level). Tensor describes inference results on :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>` level. :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>` also provides access to underlying GstBuffer and GstVideoInfo describing frame's video information (such as image width, height, channels, strides, etc.). You also can get cv::Mat object representing this video frame.

Methods
-------

.. index:: pair: function; __init__
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a6e80b69e5fc02be56888cc1f9defe1a9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def __init__(
		self self,
		Gst.Buffer buffer,
		GstVideo.VideoInfo video_info = None,
		Gst.Caps caps = None
	)

Construct :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>` instance from Gst.Buffer and GstVideo.VideoInfo or Gst.Caps.

The preferred way of creating :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>` is to use Gst.Buffer and GstVideo.VideoInfo



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- Gst.Buffer to which metadata is attached and retrieved

	*
		- video_info

		- GstVideo.VideoInfo containing video information

	*
		- caps

		- Gst.Caps from which video information is obtained

.. index:: pair: function; video_meta
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a660a083a7c0827e3e05b837f3b19db56:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstVideo.VideoMeta video_meta(self self)

Get video metadata of buffer.



.. rubric:: Returns:

GstVideo.VideoMeta of buffer, nullptr if no GstVideo.VideoMeta available

.. index:: pair: function; video_info
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1ab20943e0804b2f72effefb587389877f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstVideo.VideoInfo video_info(self self)

Get GstVideo.VideoInfo of this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.

This is preferrable way of getting any image information



.. rubric:: Returns:

GstVideo.VideoInfo of this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`

.. index:: pair: function; regions
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a1e8dc83ad23ea3f503c6354abaf8fc53:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def regions(self self)

Get RegionOfInterest objects attached to :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Returns:

iterator of RegionOfInterest objects attached to :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`

.. index:: pair: function; tensors
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a77d5b23d5e7b94b4c8ce376d05fb6f8d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def tensors(self self)

Get Tensor objects attached to :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Returns:

iterator of Tensor objects attached to :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`

.. index:: pair: function; add_region
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a91d71fb1082fb075250c8cc10bbed2c2:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`RegionOfInterest<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` add_region(
		self self,
		x x,
		y y,
		w w,
		h h,
		str label = "",
		float confidence = 0.0,
		bool normalized = False
	)

Attach RegionOfInterest to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- x

		- x coordinate of the upper left corner of bounding box

	*
		- y

		- y coordinate of the upper left corner of bounding box

	*
		- w

		- bounding box width

	*
		- h

		- bounding box height

	*
		- label

		- object label

	*
		- confidence

		- detection confidence

	*
		- region_tensor

		- base tensor for detection Tensor which will be added to this new

	*
		- normalized

		- if True, input coordinates are assumed to be normalized (in [0,1] interval). If False, input coordinates are assumed to be expressed in pixels (this is behavior by default)



.. rubric:: Returns:

new RegionOfInterest instance

.. index:: pair: function; add_tensor
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1aad298cbe68a61de4de8906d68ec180c2:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` add_tensor(self self)

Attach empty Tensor to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Returns:

new Tensor instance

.. index:: pair: function; messages
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a160a71ad120bcec8bd79180c5b3eacfb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	List[str] messages(self self)

Get messages attached to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Returns:

messages attached to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`

.. index:: pair: function; add_message
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a2139fee1f13df31bf32a5fc4f04ac63d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def add_message(self self, str message)

Attach message to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- message

		- message to attach to this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`

.. index:: pair: function; remove_message
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a16155c418a3f52d137ad2851af529bd4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def remove_message(self self, str message)

Remove message from this :ref:`VideoFrame <doxid-classgstgva_1_1video__frame_1_1_video_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- message

		- message to remove

.. index:: pair: function; remove_region
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a2a0ddef58a7550cb5d9f83a5a9cb9e22:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	None remove_region(self self, roi roi)

Remove region with the specified index.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- roi

		- Region to remove

.. index:: pair: function; data
.. _doxid-classgstgva_1_1video__frame_1_1_video_frame_1a4efa6760f87f7a2fa6560a01089d5ed7:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	numpy.ndarray data(self self, Gst.MapFlags flag = Gst.MapFlags.READ)

Get buffer data wrapped by numpy.ndarray.



.. rubric:: Returns:

numpy array instance

