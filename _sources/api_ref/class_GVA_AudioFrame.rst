.. index:: pair: class; GVA::AudioFrame
.. _doxid-class_g_v_a_1_1_audio_frame:

class GVA::AudioFrame
=====================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents audio frame - object for working with :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` and :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects which belong to this audio frame . :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` describes detected object (segments) and its :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results on :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` level). :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` describes inference results on :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` level. :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` also provides access to underlying GstBuffer and GstAudioInfo describing frame's audio information (such as format, channels, etc.). :ref:`More...<details-class_g_v_a_1_1_audio_frame>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <audio_frame.h>
	
	class AudioFrame {
	public:
		// construction
	
		:ref:`AudioFrame<doxid-class_g_v_a_1_1_audio_frame_1a7b8bc05023783e62cf640486a55f816f>`(GstBuffer* buffer, GstAudioInfo* info);
		:ref:`AudioFrame<doxid-class_g_v_a_1_1_audio_frame_1aa6cf5ebb87d3919bb4120add9f72e7ec>`(GstBuffer* buffer, const GstCaps* caps);
		:ref:`AudioFrame<doxid-class_g_v_a_1_1_audio_frame_1a2ab8ecdcf4e5a14169af7cc212b4e498>`(GstBuffer* buffer);

		// methods
	
		GstAudioMeta* :ref:`audio_meta<doxid-class_g_v_a_1_1_audio_frame_1afb8e875e122bebe45c4109080390c822>`();
		GstAudioInfo* :ref:`audio_info<doxid-class_g_v_a_1_1_audio_frame_1aaf43c4e3c8ab1aa3e395757a7941bce0>`();
		std::vector<:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`> :ref:`events<doxid-class_g_v_a_1_1_audio_frame_1a056c170570e72444c4d845fda3a57830>`();
		const std::vector<:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`> :ref:`events<doxid-class_g_v_a_1_1_audio_frame_1a82e5eeb3901441dab9f8efe5aa970acc>`() const;
		std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_audio_frame_1a8697986008fda3eed381fda6005ed3bb>`();
		const std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_audio_frame_1a94bbf4039396346b017de7d869b60714>`() const;
		std::vector<std::string> :ref:`messages<doxid-class_g_v_a_1_1_audio_frame_1a736df4f005ba9e7e803fa8e22660aa35>`();
	
		:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>` :ref:`add_event<doxid-class_g_v_a_1_1_audio_frame_1a20db0d03b167751a4b148151904de3d3>`(
			long start_time,
			long end_time,
			std::string label = std::string(),
			double confidence = 0.0
		);
	
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`add_tensor<doxid-class_g_v_a_1_1_audio_frame_1a841fc1b3078aaed9cb90058c8ed98bdc>`();
		void :ref:`add_message<doxid-class_g_v_a_1_1_audio_frame_1a9c76ec652e45683a8a9cd78dd36bb7eb>`(const std::string& message);
		void :ref:`remove_event<doxid-class_g_v_a_1_1_audio_frame_1ae90638b83ffa426c593835cac6259a55>`(const :ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`& event);
		void :ref:`remove_tensor<doxid-class_g_v_a_1_1_audio_frame_1ac33ff0f02ee4ee09eea0fccb47cac240>`(const :ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`& tensor);
	};
.. _details-class_g_v_a_1_1_audio_frame:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents audio frame - object for working with :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` and :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects which belong to this audio frame . :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` describes detected object (segments) and its :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results on :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` level). :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` describes inference results on :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` level. :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` also provides access to underlying GstBuffer and GstAudioInfo describing frame's audio information (such as format, channels, etc.).

Construction
------------

.. index:: pair: function; AudioFrame
.. _doxid-class_g_v_a_1_1_audio_frame_1a7b8bc05023783e62cf640486a55f816f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	AudioFrame(GstBuffer* buffer, GstAudioInfo* info)

Construct :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` instance from GstBuffer and GstAudioInfo. This is preferred way of creating :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

	*
		- info

		- GstAudioInfo* containing audio information

.. index:: pair: function; AudioFrame
.. _doxid-class_g_v_a_1_1_audio_frame_1aa6cf5ebb87d3919bb4120add9f72e7ec:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	AudioFrame(GstBuffer* buffer, const GstCaps* caps)

Construct :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` instance from GstBuffer and GstCaps.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

	*
		- caps

		- GstCaps* from which audio information is obtained

.. index:: pair: function; AudioFrame
.. _doxid-class_g_v_a_1_1_audio_frame_1a2ab8ecdcf4e5a14169af7cc212b4e498:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	AudioFrame(GstBuffer* buffer)

Construct :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>` instance from GstBuffer. Audio information will be obtained from buffer. This is not recommended way of creating :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`, because it relies on GstAudioMeta which can be absent for the buffer.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* to which metadata is attached and retrieved

Methods
-------

.. index:: pair: function; audio_meta
.. _doxid-class_g_v_a_1_1_audio_frame_1afb8e875e122bebe45c4109080390c822:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstAudioMeta* audio_meta()

Get audio metadata of buffer.



.. rubric:: Returns:

GstAudioMeta of buffer, nullptr if no GstAudioMeta available

.. index:: pair: function; audio_info
.. _doxid-class_g_v_a_1_1_audio_frame_1aaf43c4e3c8ab1aa3e395757a7941bce0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstAudioInfo* audio_info()

Get GstAudioInfo of this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`. This is preferrable way of getting audio information.



.. rubric:: Returns:

GstAudioInfo of this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; events
.. _doxid-class_g_v_a_1_1_audio_frame_1a056c170570e72444c4d845fda3a57830:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`> events()

Get :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

vector of :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; events
.. _doxid-class_g_v_a_1_1_audio_frame_1a82e5eeb3901441dab9f8efe5aa970acc:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const std::vector<:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`> events() const

Get :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

vector of :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_audio_frame_1a8697986008fda3eed381fda6005ed3bb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors()

Get :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_audio_frame_1a94bbf4039396346b017de7d869b60714:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors() const

Get :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached to :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; messages
.. _doxid-class_g_v_a_1_1_audio_frame_1a736df4f005ba9e7e803fa8e22660aa35:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<std::string> messages()

Get messages attached to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

messages attached to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; add_event
.. _doxid-class_g_v_a_1_1_audio_frame_1a20db0d03b167751a4b148151904de3d3:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>` add_event(
		long start_time,
		long end_time,
		std::string label = std::string(),
		double confidence = 0.0
	)

Attach :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`. This function takes ownership of event_tensor, if passed @start_time: start time stamp of the segment @end_time: end time stamp of the segment.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- label

		- object label

	*
		- confidence

		- detection confidence



.. rubric:: Returns:

new :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` instance

.. index:: pair: function; add_tensor
.. _doxid-class_g_v_a_1_1_audio_frame_1a841fc1b3078aaed9cb90058c8ed98bdc:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` add_tensor()

Attach empty :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Returns:

new :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance

.. index:: pair: function; add_message
.. _doxid-class_g_v_a_1_1_audio_frame_1a9c76ec652e45683a8a9cd78dd36bb7eb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void add_message(const std::string& message)

Attach message to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- message

		- message to attach to this :ref:`AudioFrame <doxid-class_g_v_a_1_1_audio_frame>`

.. index:: pair: function; remove_event
.. _doxid-class_g_v_a_1_1_audio_frame_1ae90638b83ffa426c593835cac6259a55:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void remove_event(const :ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event>`& event)

Remove :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- event

		- the :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` to remove

.. index:: pair: function; remove_tensor
.. _doxid-class_g_v_a_1_1_audio_frame_1ac33ff0f02ee4ee09eea0fccb47cac240:

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

