.. index:: pair: enum; GVALayout
.. _doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14ed:

enum GVALayout
==============

Overview
~~~~~~~~

This enum describes model layer layout. :ref:`More...<details-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14ed>`

.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gva_tensor_meta.h>

	enum GVALayout {
	    :ref:`GVA_LAYOUT_ANY<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14edaea9dad2ce8b344d5394be5d8174916e5>`  = 0,
	    :ref:`GVA_LAYOUT_NCHW<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda7fb1135aad3612cccafb433dc0f2abd9>` = 1,
	    :ref:`GVA_LAYOUT_NHWC<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda4dcfeb32722ce4821c465192200f0d29>` = 2,
	    :ref:`GVA_LAYOUT_NC<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda7147907fd1907e376d2350ea18262cf9>`   = 193,
	};

.. _details-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14ed:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This enum describes model layer layout.

Enum Values
-----------

.. index:: pair: enumvalue; GVA_LAYOUT_ANY
.. _doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14edaea9dad2ce8b344d5394be5d8174916e5:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_LAYOUT_ANY

unspecified layout

.. index:: pair: enumvalue; GVA_LAYOUT_NCHW
.. _doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda7fb1135aad3612cccafb433dc0f2abd9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_LAYOUT_NCHW

NCWH layout

.. index:: pair: enumvalue; GVA_LAYOUT_NHWC
.. _doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda4dcfeb32722ce4821c465192200f0d29:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_LAYOUT_NHWC

NHWC layout

.. index:: pair: enumvalue; GVA_LAYOUT_NC
.. _doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14eda7147907fd1907e376d2350ea18262cf9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_LAYOUT_NC

NC layout

