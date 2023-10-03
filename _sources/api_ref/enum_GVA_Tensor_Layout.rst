.. index:: pair: enum; Layout
.. _doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650:

enum GVA::Tensor::Layout
========================

Overview
~~~~~~~~

Describes tensor layout. :ref:`More...<details-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>`

.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>

	enum Layout {
	    :ref:`ANY<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a8e1bde3c3d303163521522cf1d62f21f>`  = GVA_LAYOUT_ANY,
	    :ref:`NCHW<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a6b99f356fe3b30a2a850b5ea897c289f>` = GVA_LAYOUT_NCHW,
	    :ref:`NHWC<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650ad066db54b89b0912e7e7c6da51e2da51>` = GVA_LAYOUT_NHWC,
	    :ref:`NC<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a90581d96b500fd2d3fd701a583409cb8>`   = GVA_LAYOUT_NC,
	};

.. _details-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Describes tensor layout.

Enum Values
-----------

.. index:: pair: enumvalue; ANY
.. _doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a8e1bde3c3d303163521522cf1d62f21f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	ANY

unspecified layout

.. index:: pair: enumvalue; NCHW
.. _doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a6b99f356fe3b30a2a850b5ea897c289f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	NCHW

NCWH layout

.. index:: pair: enumvalue; NHWC
.. _doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650ad066db54b89b0912e7e7c6da51e2da51:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	NHWC

NHWC layout

.. index:: pair: enumvalue; NC
.. _doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a90581d96b500fd2d3fd701a583409cb8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	NC

NC layout

