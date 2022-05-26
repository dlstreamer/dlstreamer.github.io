.. index:: pair: enum; Precision
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee:

enum GVA::Tensor::Precision
===========================

Overview
~~~~~~~~

Describes tensor precision. :ref:`More...<details-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>`

.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>

	enum Precision {
	    :ref:`UNSPECIFIED<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea1c04cc3823d476c3017238679a0fdf52>` = GVA_PRECISION_UNSPECIFIED,
	    :ref:`FP32<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea693aa0bef84c25fe81c7e62e72f9313d>`        = GVA_PRECISION_FP32,
	    :ref:`FP16<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaa4bf99d6945c25077fd6660d536af8a0>`        = GVA_PRECISION_FP16,
	    :ref:`BF16<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaf656bbf613964dcf710b771b0918ab30>`        = GVA_PRECISION_BF16,
	    :ref:`FP64<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3fc58a0c61fb59a7689728a045f2edbb>`        = GVA_PRECISION_FP64,
	    :ref:`Q78<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3b5c22a200e137c7b7cec9ee3076aa7b>`         = GVA_PRECISION_Q78,
	    :ref:`I16<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeabcd774f891b5f9df7099f3ea75dadf8d>`         = GVA_PRECISION_I16,
	    :ref:`U4<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea7a7e060fbac468049775df37d8dfa511>`          = GVA_PRECISION_U4,
	    :ref:`U8<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea6669348b484e3008dca2bfa8e85e40b5>`          = GVA_PRECISION_U8,
	    :ref:`I4<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3542ac61a301c83960ca9c44a79260e9>`          = GVA_PRECISION_I4,
	    :ref:`I8<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea5aef4e3ea379fa0eb2bf42d979443902>`          = GVA_PRECISION_I8,
	    :ref:`U16<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaef9ef3ebca4d2b64b6ec83808bafa5f2>`         = GVA_PRECISION_U16,
	    :ref:`I32<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeead878ea6016bfe01729548bf442de5a8b>`         = GVA_PRECISION_I32,
	    :ref:`U32<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeac8bd5bedff8ef192d39a962afc0e19ee>`         = GVA_PRECISION_U32,
	    :ref:`I64<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeae7e62f6928f76df671b5a0379793fab6>`         = GVA_PRECISION_I64,
	    :ref:`U64<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea31d65cccd6593e4101db93fb878abcaa>`         = GVA_PRECISION_U64,
	    :ref:`BIN<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea35d3245a21b0942070419ef6602d239e>`         = GVA_PRECISION_BIN,
	    :ref:`BOOL<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaa97b2c144243b2b9d2c593ec268b62f5>`        = GVA_PRECISION_BOOL,
	    :ref:`CUSTOM<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea72baef04098f035e8a320b03ad197818>`      = GVA_PRECISION_CUSTOM,
	};

.. _details-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Describes tensor precision.

Enum Values
-----------

.. index:: pair: enumvalue; UNSPECIFIED
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea1c04cc3823d476c3017238679a0fdf52:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	UNSPECIFIED

default value

.. index:: pair: enumvalue; FP32
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea693aa0bef84c25fe81c7e62e72f9313d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	FP32

32bit floating point value

.. index:: pair: enumvalue; FP16
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaa4bf99d6945c25077fd6660d536af8a0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	FP16

16bit floating point value, 5 bit for exponent, 10 bit for mantisa

.. index:: pair: enumvalue; BF16
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaf656bbf613964dcf710b771b0918ab30:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	BF16

16bit floating point value, 8 bit for exponent, 7 bit for mantisa

.. index:: pair: enumvalue; FP64
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3fc58a0c61fb59a7689728a045f2edbb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	FP64

64bit floating point value

.. index:: pair: enumvalue; Q78
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3b5c22a200e137c7b7cec9ee3076aa7b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	Q78

16bit specific signed fixed point precision

.. index:: pair: enumvalue; I16
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeabcd774f891b5f9df7099f3ea75dadf8d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	I16

16bit signed integer value

.. index:: pair: enumvalue; U4
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea7a7e060fbac468049775df37d8dfa511:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	U4

4bit unsigned integer value

.. index:: pair: enumvalue; U8
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea6669348b484e3008dca2bfa8e85e40b5:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	U8

unsigned 8bit integer value

.. index:: pair: enumvalue; I4
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea3542ac61a301c83960ca9c44a79260e9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	I4

4bit signed integer value

.. index:: pair: enumvalue; I8
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea5aef4e3ea379fa0eb2bf42d979443902:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	I8

8bit signed integer value

.. index:: pair: enumvalue; U16
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaef9ef3ebca4d2b64b6ec83808bafa5f2:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	U16

16bit unsigned integer value

.. index:: pair: enumvalue; I32
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeead878ea6016bfe01729548bf442de5a8b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	I32

32bit signed integer value

.. index:: pair: enumvalue; U32
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeac8bd5bedff8ef192d39a962afc0e19ee:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	U32

32bit unsigned integer value

.. index:: pair: enumvalue; I64
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeae7e62f6928f76df671b5a0379793fab6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	I64

64bit signed integer value

.. index:: pair: enumvalue; U64
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea31d65cccd6593e4101db93fb878abcaa:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	U64

64bit unsigned integer value

.. index:: pair: enumvalue; BIN
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea35d3245a21b0942070419ef6602d239e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	BIN

1bit integer value

.. index:: pair: enumvalue; BOOL
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeeaa97b2c144243b2b9d2c593ec268b62f5:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	BOOL

8bit bool type

.. index:: pair: enumvalue; CUSTOM
.. _doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea72baef04098f035e8a320b03ad197818:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	CUSTOM

custom precision has it's own name and size of elements

