.. index:: pair: struct; _GstGVATensorMeta
.. _doxid-struct___gst_g_v_a_tensor_meta:

struct _GstGVATensorMeta
========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This struct represents raw tensor metadata and contains instance of parent GstMeta and fields describing inference result tensor. This metadata instances is attached to buffer by gvainference elements. :ref:`More...<details-struct___gst_g_v_a_tensor_meta>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gva_tensor_meta.h>
	
	struct _GstGVATensorMeta {
		// fields
	
		GstMeta :ref:`meta<doxid-struct___gst_g_v_a_tensor_meta_1a783c8f44e6840bf8ec50414a0050874e>`;
		GstStructure* :ref:`data<doxid-struct___gst_g_v_a_tensor_meta_1adaf587348b4d4196c00e1b456272bbf4>`;
	};
.. _details-struct___gst_g_v_a_tensor_meta:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This struct represents raw tensor metadata and contains instance of parent GstMeta and fields describing inference result tensor. This metadata instances is attached to buffer by gvainference elements.

Fields
------

.. index:: pair: variable; meta
.. _doxid-struct___gst_g_v_a_tensor_meta_1a783c8f44e6840bf8ec50414a0050874e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstMeta meta

parent meta object

.. index:: pair: variable; data
.. _doxid-struct___gst_g_v_a_tensor_meta_1adaf587348b4d4196c00e1b456272bbf4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstStructure* data

pointer to GstStructure data contains: precision, rank, array tensor's dimensions, layout, output layer name, model name, tensor data, tensor size, id of GStreamer pipeline element

