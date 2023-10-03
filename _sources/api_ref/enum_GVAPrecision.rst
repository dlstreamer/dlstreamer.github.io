.. index:: pair: enum; GVAPrecision
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ce:

enum GVAPrecision
=================

Overview
~~~~~~~~

This enum describes model layer precision. :ref:`More...<details-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ce>`

.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <gva_tensor_meta.h>

	enum GVAPrecision {
	    :ref:`GVA_PRECISION_UNSPECIFIED<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea28476a6525b1d4fe1f8e8882bdfe5d6e>` = 255,
	    :ref:`GVA_PRECISION_FP32<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea9be31ded971c1fe2b9d8307c460a1c28>`        = 10,
	    :ref:`GVA_PRECISION_FP16<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaa261d349bdc91cdd2cf06fac2bafb85e>`        = 11,
	    :ref:`GVA_PRECISION_BF16<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceacd87ce4aa5e4bd89dd2d6f9def1b04b9>`        = 12,
	    :ref:`GVA_PRECISION_FP64<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea622212209079404716a501d74db0187c>`        = 13,
	    :ref:`GVA_PRECISION_Q78<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea461b72923c37d9eb095493943370b4b4>`         = 20,
	    :ref:`GVA_PRECISION_I16<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae8c3e6dceda5f34b636830f6d0248005>`         = 30,
	    :ref:`GVA_PRECISION_U4<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaa6ff18df48e8730bb548ebea3b13b65b>`          = 39,
	    :ref:`GVA_PRECISION_U8<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea88c3e9afd5d03d97e7baf46f124df0f0>`          = 40,
	    :ref:`GVA_PRECISION_I4<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae72894568612e0a54195320bce8e4b3e>`          = 49,
	    :ref:`GVA_PRECISION_I8<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea80ba446ab097f5c4bdddc00c3f2d9c0a>`          = 50,
	    :ref:`GVA_PRECISION_U16<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea99847e16356c8a7fb2d9b4254d63b867>`         = 60,
	    :ref:`GVA_PRECISION_I32<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea8ee7c0b02fd09012e50f7be3812c45b4>`         = 70,
	    :ref:`GVA_PRECISION_U32<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaf1e2edffdfcdc9951a41e2e17693007c>`         = 74,
	    :ref:`GVA_PRECISION_I64<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaafb2eb2fedd98b36ce5fced93bbbb110>`         = 72,
	    :ref:`GVA_PRECISION_U64<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae90ec3f9bf1e6d97c269eb0790f43b3a>`         = 73,
	    :ref:`GVA_PRECISION_BIN<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaccea4965077151e3e8981202f92444de>`         = 71,
	    :ref:`GVA_PRECISION_BOOL<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea8dba8160588a6de7f66a437905eb9ff8>`        = 41,
	    :ref:`GVA_PRECISION_CUSTOM<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaf0315c9dd1508288a2cc0083d3cd03b8>`      = 80,
	};

.. _details-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ce:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This enum describes model layer precision.

Enum Values
-----------

.. index:: pair: enumvalue; GVA_PRECISION_UNSPECIFIED
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea28476a6525b1d4fe1f8e8882bdfe5d6e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_UNSPECIFIED

default value

.. index:: pair: enumvalue; GVA_PRECISION_FP32
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea9be31ded971c1fe2b9d8307c460a1c28:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_FP32

32bit floating point value

.. index:: pair: enumvalue; GVA_PRECISION_FP16
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaa261d349bdc91cdd2cf06fac2bafb85e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_FP16

16bit floating point value, 5 bit for exponent, 10 bit for mantisa

.. index:: pair: enumvalue; GVA_PRECISION_BF16
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceacd87ce4aa5e4bd89dd2d6f9def1b04b9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_BF16

16bit floating point value, 8 bit for exponent, 7 bit for mantisa

.. index:: pair: enumvalue; GVA_PRECISION_FP64
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea622212209079404716a501d74db0187c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_FP64

64bit floating point value

.. index:: pair: enumvalue; GVA_PRECISION_Q78
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea461b72923c37d9eb095493943370b4b4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_Q78

16bit specific signed fixed point precision

.. index:: pair: enumvalue; GVA_PRECISION_I16
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae8c3e6dceda5f34b636830f6d0248005:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_I16

16bit signed integer value

.. index:: pair: enumvalue; GVA_PRECISION_U4
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaa6ff18df48e8730bb548ebea3b13b65b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_U4

4bit unsigned integer value

.. index:: pair: enumvalue; GVA_PRECISION_U8
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea88c3e9afd5d03d97e7baf46f124df0f0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_U8

unsignned 8bit integer value

.. index:: pair: enumvalue; GVA_PRECISION_I4
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae72894568612e0a54195320bce8e4b3e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_I4

4bit signed integer value

.. index:: pair: enumvalue; GVA_PRECISION_I8
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea80ba446ab097f5c4bdddc00c3f2d9c0a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_I8

8bit signed integer value

.. index:: pair: enumvalue; GVA_PRECISION_U16
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea99847e16356c8a7fb2d9b4254d63b867:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_U16

16bit unsigned integer value

.. index:: pair: enumvalue; GVA_PRECISION_I32
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea8ee7c0b02fd09012e50f7be3812c45b4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_I32

32bit signed integer value

.. index:: pair: enumvalue; GVA_PRECISION_U32
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaf1e2edffdfcdc9951a41e2e17693007c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_U32

32bit unsigned integer value

.. index:: pair: enumvalue; GVA_PRECISION_I64
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaafb2eb2fedd98b36ce5fced93bbbb110:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_I64

64bit signed integer value

.. index:: pair: enumvalue; GVA_PRECISION_U64
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceae90ec3f9bf1e6d97c269eb0790f43b3a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_U64

64bit unsigned integer value

.. index:: pair: enumvalue; GVA_PRECISION_BIN
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaccea4965077151e3e8981202f92444de:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_BIN

1bit integer value

.. index:: pair: enumvalue; GVA_PRECISION_BOOL
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795cea8dba8160588a6de7f66a437905eb9ff8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_BOOL

8bit bool type

.. index:: pair: enumvalue; GVA_PRECISION_CUSTOM
.. _doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ceaf0315c9dd1508288a2cc0083d3cd03b8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GVA_PRECISION_CUSTOM

custom precision has it's own name and size of elements

