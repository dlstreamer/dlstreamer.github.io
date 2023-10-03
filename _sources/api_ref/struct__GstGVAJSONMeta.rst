.. index:: pair: struct; _GstGVAJSONMeta
.. _doxid-struct___gst_g_v_a_j_s_o_n_meta:

struct _GstGVAJSONMeta
======================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This struct represents JSON metadata and contains instance of parent GstMeta and message. :ref:`More...<details-struct___gst_g_v_a_j_s_o_n_meta>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gva_json_meta.h>
	
	struct _GstGVAJSONMeta {
		// fields
	
		GstMeta :ref:`meta<doxid-struct___gst_g_v_a_j_s_o_n_meta_1a6b1f3346ccaf460a145b3a94d665d693>`;
		gchar* :ref:`message<doxid-struct___gst_g_v_a_j_s_o_n_meta_1ad979e308bc05378285a790845939a91a>`;
	};
.. _details-struct___gst_g_v_a_j_s_o_n_meta:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This struct represents JSON metadata and contains instance of parent GstMeta and message.

Fields
------

.. index:: pair: variable; meta
.. _doxid-struct___gst_g_v_a_j_s_o_n_meta_1a6b1f3346ccaf460a145b3a94d665d693:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstMeta meta

parent GstMeta

.. index:: pair: variable; message
.. _doxid-struct___gst_g_v_a_j_s_o_n_meta_1ad979e308bc05378285a790845939a91a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	gchar* message

C-string message

