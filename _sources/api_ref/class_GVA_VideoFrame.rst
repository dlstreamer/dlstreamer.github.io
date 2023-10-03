.. index:: pair: class; GVA::VideoFrame
.. _doxid-class_g_v_a_1_1_video_frame:

class GVA::VideoFrame
=====================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents video frame - object for working with :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` and :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects which belong to this video frame (image). :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` describes detected object (bounding boxes) and its :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results on :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` level). :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` describes inference results on :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` level. :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` also provides access to underlying GstBuffer and GstVideoInfo describing frame's video information (such as image width, height, channels, strides, etc.). You also can get cv::Mat object representing this video frame. :ref:`More...<details-class_g_v_a_1_1_video_frame>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <video_frame.h>
	
	class VideoFrame {
	public:
		// construction
	
		:ref:`VideoFrame<doxid-class_g_v_a_1_1_video_frame_1aca096338a0d5dcb76c5db53a5bb3682a>`(GstBuffer* buffer, GstVideoInfo* info);
		:ref:`VideoFrame<doxid-class_g_v_a_1_1_video_frame_1abc329d6193ddf753d5bb3223388b3fca>`(GstBuffer* buffer, const GstCaps* caps);
		:ref:`VideoFrame<doxid-class_g_v_a_1_1_video_frame_1a0b719b642298a2502e331ab1b5fdfb8d>`(GstBuffer* buffer);

		// methods
	
		GstVideoMeta* :ref:`video_meta<doxid-class_g_v_a_1_1_video_frame_1afcebeba6ae2062d5ad080404c6b7179d>`();
		GstVideoInfo* :ref:`video_info<doxid-class_g_v_a_1_1_video_frame_1aaf3ae701e8a25be45468cf8735dc98e0>`();
		std::vector<:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`> :ref:`regions<doxid-class_g_v_a_1_1_video_frame_1a763089d59a8a35bae1c2cde108d826e1>`();
		const std::vector<:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`> :ref:`regions<doxid-class_g_v_a_1_1_video_frame_1a46d9fd55c4d146e5988aee35e171ce43>`() const;
		std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_video_frame_1acc2cb5f65c9dd25c2cf82387df943e06>`();
		const std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_video_frame_1a391619c3b055d16c2df41e2003f7fa4a>`() const;
		std::vector<std::string> :ref:`messages<doxid-class_g_v_a_1_1_video_frame_1a9aae9654d09d9523365f785ad68e4d84>`();
	
		:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>` :ref:`add_region<doxid-class_g_v_a_1_1_video_frame_1a890a49a3959934594df428b032d4fed7>`(
			double x,
			double y,
			double w,
			double h,
			std::string label = std::string(),
			double confidence = 0.0,
			bool normalized = false
		);
	
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`add_tensor<doxid-class_g_v_a_1_1_video_frame_1a859814356539bca6ec974bdc3d4c7660>`();
		void :ref:`add_message<doxid-class_g_v_a_1_1_video_frame_1a9ece64c974e4d68edd3f004464c2f19d>`(const std::string& message);
		void :ref:`remove_region<doxid-class_g_v_a_1_1_video_frame_1ad4be443a009d280d2572a59cf85f6aaa>`(const :ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`& roi);
		void :ref:`remove_tensor<doxid-class_g_v_a_1_1_video_frame_1a884683d4ca1c4d83bea0a88c3b832c5a>`(const :ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`& tensor);
	};
.. _details-class_g_v_a_1_1_video_frame:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents video frame - object for working with :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` and :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects which belong to this video frame (image). :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` describes detected object (bounding boxes) and its :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results on :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` level). :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` describes inference results on :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` level. :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` also provides access to underlying GstBuffer and GstVideoInfo describing frame's video information (such as image width, height, channels, strides, etc.). You also can get cv::Mat object representing this video frame.

Construction
------------

.. index:: pair: function; VideoFrame
.. _doxid-class_g_v_a_1_1_video_frame_1aca096338a0d5dcb76c5db53a5bb3682a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	VideoFrame(GstBuffer* buffer, GstVideoInfo* info)

Construct :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instance from GstBuffer and GstVideoInfo. This is preferred way of creating :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

	*
		- info

		- GstVideoInfo* containing video information

.. index:: pair: function; VideoFrame
.. _doxid-class_g_v_a_1_1_video_frame_1abc329d6193ddf753d5bb3223388b3fca:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	VideoFrame(GstBuffer* buffer, const GstCaps* caps)

Construct :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instance from GstBuffer and GstCaps.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

	*
		- caps

		- GstCaps* from which video information is obtained

.. index:: pair: function; VideoFrame
.. _doxid-class_g_v_a_1_1_video_frame_1a0b719b642298a2502e331ab1b5fdfb8d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	VideoFrame(GstBuffer* buffer)

Construct :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instance from GstBuffer. Video information will be obtained from buffer. This is not recommended way of creating :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`, because it relies on GstVideoMeta which can be absent for the buffer.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

Methods
-------

.. index:: pair: function; video_meta
.. _doxid-class_g_v_a_1_1_video_frame_1afcebeba6ae2062d5ad080404c6b7179d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstVideoMeta* video_meta()

Get video metadata of buffer.



.. rubric:: Returns:

GstVideoMeta of buffer, nullptr if no GstVideoMeta available

.. index:: pair: function; video_info
.. _doxid-class_g_v_a_1_1_video_frame_1aaf3ae701e8a25be45468cf8735dc98e0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstVideoInfo* video_info()

Get GstVideoInfo of this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`. This is preferrable way of getting any image information.



.. rubric:: Returns:

GstVideoInfo of this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; regions
.. _doxid-class_g_v_a_1_1_video_frame_1a763089d59a8a35bae1c2cde108d826e1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`> regions()

Get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

vector of :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; regions
.. _doxid-class_g_v_a_1_1_video_frame_1a46d9fd55c4d146e5988aee35e171ce43:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const std::vector<:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`> regions() const

Get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

vector of :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_video_frame_1acc2cb5f65c9dd25c2cf82387df943e06:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors()

Get :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_video_frame_1a391619c3b055d16c2df41e2003f7fa4a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors() const

Get :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; messages
.. _doxid-class_g_v_a_1_1_video_frame_1a9aae9654d09d9523365f785ad68e4d84:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<std::string> messages()

Get messages attached to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

messages attached to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; add_region
.. _doxid-class_g_v_a_1_1_video_frame_1a890a49a3959934594df428b032d4fed7:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>` add_region(
		double x,
		double y,
		double w,
		double h,
		std::string label = std::string(),
		double confidence = 0.0,
		bool normalized = false
	)

Attach :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`. This function takes ownership of region_tensor, if passed.



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

		- width of the bounding box

	*
		- h

		- height of the bounding box

	*
		- label

		- object label

	*
		- confidence

		- detection confidence

	*
		- normalized

		- if False, bounding box coordinates are pixel coordinates in range from 0 to image width/height. if True, bounding box coordinates normalized to [0,1] range.



.. rubric:: Returns:

new :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` instance

.. index:: pair: function; add_tensor
.. _doxid-class_g_v_a_1_1_video_frame_1a859814356539bca6ec974bdc3d4c7660:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` add_tensor()

Attach empty :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Returns:

new :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance

.. index:: pair: function; add_message
.. _doxid-class_g_v_a_1_1_video_frame_1a9ece64c974e4d68edd3f004464c2f19d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void add_message(const std::string& message)

Attach message to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- message

		- message to attach to this :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>`

.. index:: pair: function; remove_region
.. _doxid-class_g_v_a_1_1_video_frame_1ad4be443a009d280d2572a59cf85f6aaa:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void remove_region(const :ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest>`& roi)

Remove :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- roi

		- the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` to remove

.. index:: pair: function; remove_tensor
.. _doxid-class_g_v_a_1_1_video_frame_1a884683d4ca1c4d83bea0a88c3b832c5a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void remove_tensor(const :ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`& tensor)

Remove :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- tensor

		- the :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` to remove

