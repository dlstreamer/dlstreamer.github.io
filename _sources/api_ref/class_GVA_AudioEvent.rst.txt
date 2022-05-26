.. index:: pair: class; GVA::AudioEvent
.. _doxid-class_g_v_a_1_1_audio_event:

class GVA::AudioEvent
=====================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents audio event - object describing audio event detection result (segment) and containing multiple :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results) attached by multiple models. For example, it can be audio event with detected speech and converts speech to text. It can be produced by a pipeline with gvaaudiodetect with detection model and gvaspeechtotext element with speechtotext model. Such :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` will have start and end timestamps filled and will have 2 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached - 1 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object with detection result and other with speech to text tensor objectresult. :ref:`More...<details-class_g_v_a_1_1_audio_event>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <audio_event.h>
	
	class AudioEvent {
	public:
		// construction
	
		:ref:`AudioEvent<doxid-class_g_v_a_1_1_audio_event_1ac2248d35a41ef7f1c1ae11d2c7622fb3>`(:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta);

		// methods
	
		:ref:`Segment<doxid-struct_g_v_a_1_1_segment>`<gulong> :ref:`segment<doxid-class_g_v_a_1_1_audio_event_1abf8625c18e4410cc302d353d0482501b>`() const;
		std::string :ref:`label<doxid-class_g_v_a_1_1_audio_event_1a0f0dce868b5b24ce4d58f985da21ee82>`() const;
		double :ref:`confidence<doxid-class_g_v_a_1_1_audio_event_1a9bf388c2ee9ab5e472e79eb30a0cd81e>`() const;
		std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_audio_event_1ab129e5558dd825c252821c899c8fd882>`() const;
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`add_tensor<doxid-class_g_v_a_1_1_audio_event_1a744f70d539ba8f73fec6c19ecbb50048>`(const std::string& name);
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`detection<doxid-class_g_v_a_1_1_audio_event_1a2e61091c817a9f66d1f3df7930ebc6aa>`();
		int :ref:`label_id<doxid-class_g_v_a_1_1_audio_event_1a4e5c8c89553ef6dec963a56425bd5091>`() const;
		void :ref:`set_label<doxid-class_g_v_a_1_1_audio_event_1a6436e8da526e7482bf56a1fc716e509b>`(std::string label);
		:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :ref:`_meta<doxid-class_g_v_a_1_1_audio_event_1afd405cf035d5a84c85a830f14f7f430a>`() const;
	};
.. _details-class_g_v_a_1_1_audio_event:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents audio event - object describing audio event detection result (segment) and containing multiple :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results) attached by multiple models. For example, it can be audio event with detected speech and converts speech to text. It can be produced by a pipeline with gvaaudiodetect with detection model and gvaspeechtotext element with speechtotext model. Such :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` will have start and end timestamps filled and will have 2 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached - 1 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object with detection result and other with speech to text tensor objectresult.

Construction
------------

.. index:: pair: function; AudioEvent
.. _doxid-class_g_v_a_1_1_audio_event_1ac2248d35a41ef7f1c1ae11d2c7622fb3:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	AudioEvent(:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta)

Construct :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` instance from :ref:`GstGVAAudioEventMeta <doxid-struct_gst_g_v_a_audio_event_meta>`. After this, :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` will obtain all tensors (detection & inference results) from :ref:`GstGVAAudioEventMeta <doxid-struct_gst_g_v_a_audio_event_meta>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- meta

		- :ref:`GstGVAAudioEventMeta <doxid-struct_gst_g_v_a_audio_event_meta>` containing AudioEVent information and tensors

Methods
-------

.. index:: pair: function; segment
.. _doxid-class_g_v_a_1_1_audio_event_1abf8625c18e4410cc302d353d0482501b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Segment<doxid-struct_g_v_a_1_1_segment>`<gulong> segment() const

Get :ref:`Segment <doxid-struct_g_v_a_1_1_segment>` of :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` as start and end timestamps, timestamps are presentation time.



.. rubric:: Returns:

Start and end time of :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`

.. index:: pair: function; label
.. _doxid-class_g_v_a_1_1_audio_event_1a0f0dce868b5b24ce4d58f985da21ee82:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string label() const

Get :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` label.



.. rubric:: Returns:

:ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` label

.. index:: pair: function; confidence
.. _doxid-class_g_v_a_1_1_audio_event_1a9bf388c2ee9ab5e472e79eb30a0cd81e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	double confidence() const

Get :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` detection confidence (set by gvaaudiodetect)



.. rubric:: Returns:

last added detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` confidence if exists, otherwise 0.0

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_audio_event_1ab129e5558dd825c252821c899c8fd882:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors() const

Get all :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instances added to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instances added to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`

.. index:: pair: function; add_tensor
.. _doxid-class_g_v_a_1_1_audio_event_1a744f70d539ba8f73fec6c19ecbb50048:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` add_tensor(const std::string& name)

Add new tensor (inference result) to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` with name set. To add detection tensor, set name to "detection".



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- name for the tensor. If name is set to "detection", detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` will be created and set for this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`



.. rubric:: Returns:

just created :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object, which can be filled with tensor information further

.. index:: pair: function; detection
.. _doxid-class_g_v_a_1_1_audio_event_1a2e61091c817a9f66d1f3df7930ebc6aa:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` detection()

Returns detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, last added to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`. As any other :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, returned detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` can contain arbitrary information. If you use :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` based on :ref:`GstGVAAudioEventMeta <doxid-struct_gst_g_v_a_audio_event_meta>` attached by gvaaudiodetect by default, then this :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` will contain "label_id", "confidence", "start_timestamp", "end_timestamp" fields. If :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` doesn't have detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, it will be created in-place.



.. rubric:: Returns:

detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, empty if there were no detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects added to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` when this method was called

.. index:: pair: function; label_id
.. _doxid-class_g_v_a_1_1_audio_event_1a4e5c8c89553ef6dec963a56425bd5091:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int label_id() const

Get label_id from detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, last added to this :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>`.



.. rubric:: Returns:

last added detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` label_id if exists, otherwise 0

.. index:: pair: function; set_label
.. _doxid-class_g_v_a_1_1_audio_event_1a6436e8da526e7482bf56a1fc716e509b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_label(std::string label)

Set :ref:`AudioEvent <doxid-class_g_v_a_1_1_audio_event>` label.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- label

		- Label to set

.. index:: pair: function; _meta
.. _doxid-class_g_v_a_1_1_audio_event_1afd405cf035d5a84c85a830f14f7f430a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* _meta() const

Internal function, don't use or use with caution.



.. rubric:: Returns:

pointer to underlying :ref:`GstGVAAudioEventMeta <doxid-struct_gst_g_v_a_audio_event_meta>`

