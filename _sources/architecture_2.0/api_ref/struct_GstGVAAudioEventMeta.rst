.. index:: pair: struct; GstGVAAudioEventMeta
.. _doxid-struct_gst_g_v_a_audio_event_meta:

struct GstGVAAudioEventMeta
===========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Extra buffer metadata describing an audio frame event details. :ref:`More...<details-struct_gst_g_v_a_audio_event_meta>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gva_audio_event_meta.h>
	
	struct GstGVAAudioEventMeta {
		// fields
	
		GstMeta :ref:`meta<doxid-struct_gst_g_v_a_audio_event_meta_1aa9e75d536dc0b26bdcd4a5244b39ff73>`;
		GQuark :ref:`event_type<doxid-struct_gst_g_v_a_audio_event_meta_1a0dacfefbf7225e0debd793de5411d32e>`;
		gint :ref:`id<doxid-struct_gst_g_v_a_audio_event_meta_1a90f4a9a1ed5700bda3c9347cf9328400>`;
		guint64 :ref:`start_timestamp<doxid-struct_gst_g_v_a_audio_event_meta_1a69e2d1983f3351a0d1e12925ab218037>`;
		guint64 :ref:`end_timestamp<doxid-struct_gst_g_v_a_audio_event_meta_1a0be03e85ec272ab042d116c900645384>`;
		GList* :ref:`params<doxid-struct_gst_g_v_a_audio_event_meta_1a1842127f10abe2ca8850864a7b350e1f>`;
	};
.. _details-struct_gst_g_v_a_audio_event_meta:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Extra buffer metadata describing an audio frame event details.

Fields
------

.. index:: pair: variable; meta
.. _doxid-struct_gst_g_v_a_audio_event_meta_1aa9e75d536dc0b26bdcd4a5244b39ff73:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstMeta meta

Parent #GstMeta

.. index:: pair: variable; event_type
.. _doxid-struct_gst_g_v_a_audio_event_meta_1a0dacfefbf7225e0debd793de5411d32e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GQuark event_type

GQuark describing the semantic of the AudioEvent (f.i. a Sound, a Speech, Silence)

.. index:: pair: variable; id
.. _doxid-struct_gst_g_v_a_audio_event_meta_1a90f4a9a1ed5700bda3c9347cf9328400:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	gint id

Identifier of this particular event

.. index:: pair: variable; start_timestamp
.. _doxid-struct_gst_g_v_a_audio_event_meta_1a69e2d1983f3351a0d1e12925ab218037:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	guint64 start_timestamp

Start time stamp of the segment

.. index:: pair: variable; end_timestamp
.. _doxid-struct_gst_g_v_a_audio_event_meta_1a0be03e85ec272ab042d116c900645384:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	guint64 end_timestamp

End time stamp of the segment

.. index:: pair: variable; params
.. _doxid-struct_gst_g_v_a_audio_event_meta_1a1842127f10abe2ca8850864a7b350e1f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GList* params

List of #GstStructure containing element-specific params for downstream, see :ref:`gst_gva_audio_event_meta_add_param() <doxid-gva__audio__event__meta_8h_1a71b5f79e7958b04f6af52821525c5b5b>`.

