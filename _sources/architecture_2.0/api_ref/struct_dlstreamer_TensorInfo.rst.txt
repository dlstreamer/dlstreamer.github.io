.. index:: pair: struct; dlstreamer::TensorInfo
.. _doxid-structdlstreamer_1_1_tensor_info:

struct dlstreamer::TensorInfo
=============================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Structure contaning tensor information - data type, shape, stride. :ref:`More...<details-structdlstreamer_1_1_tensor_info>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor_info.h>
	
	struct TensorInfo {
		// fields
	
		std::vector<size_t> :target:`shape<doxid-structdlstreamer_1_1_tensor_info_1a96449320064a1410011b2ff51a19a0bc>`;
		std::vector<size_t> :target:`stride<doxid-structdlstreamer_1_1_tensor_info_1a419bd87c9844d4ccd76841872295c160>`;
		:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` :target:`dtype<doxid-structdlstreamer_1_1_tensor_info_1aba311d00499ab0cee9e15cb98aff388f>`;

		// construction
	
		:target:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info_1a089b0bbf80b3d1cf07ab8ec26f80fe34>`();
	
		:ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info_1a4fcf4877644fd9ee66aba454fd83742e>`(
			std::vector<size_t> _shape,
			:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` _dtype = :ref:`DataType::UInt8<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82ab31df9c476d20e85ff898121efe11b5a>`,
			std::vector<size_t> _stride = {}
		);

		// methods
	
		size_t :ref:`size<doxid-structdlstreamer_1_1_tensor_info_1a29309557166a2a50bc147939407f7a44>`() const;
		size_t :ref:`itemsize<doxid-structdlstreamer_1_1_tensor_info_1ab195722d64b8d02e3d73a791e6cc6101>`() const;
		size_t :ref:`nbytes<doxid-structdlstreamer_1_1_tensor_info_1a1dbae2ea0f0a20bd9f093b4453666c7b>`() const;
		bool :ref:`is_contiguous<doxid-structdlstreamer_1_1_tensor_info_1af4051b3f5ee7c113d9d9b39ca098067a>`() const;
		bool :target:`operator <<doxid-structdlstreamer_1_1_tensor_info_1a1fe29e9370652b0c0673012d062fb3b4>` (const TensorInfo& r) const;
		bool :target:`operator ==<doxid-structdlstreamer_1_1_tensor_info_1af09f3269ece0aaadec7f887c2c711725>` (const TensorInfo& r) const;
		bool :target:`operator !=<doxid-structdlstreamer_1_1_tensor_info_1a10945e2fe356322d1b26ac5e39fc938e>` (const TensorInfo& r) const;
	};
.. _details-structdlstreamer_1_1_tensor_info:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Structure contaning tensor information - data type, shape, stride.

Construction
------------

.. index:: pair: function; TensorInfo
.. _doxid-structdlstreamer_1_1_tensor_info_1a4fcf4877644fd9ee66aba454fd83742e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	TensorInfo(
		std::vector<size_t> _shape,
		:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` _dtype = :ref:`DataType::UInt8<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82ab31df9c476d20e85ff898121efe11b5a>`,
		std::vector<size_t> _stride = {}
	)

If stride array is empty in constructor parameter, stride will be created automatically assuming contiguous memory layout without padding.

Methods
-------

.. index:: pair: function; size
.. _doxid-structdlstreamer_1_1_tensor_info_1a29309557166a2a50bc147939407f7a44:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	size_t size() const

Return number elements in tensor - multiplication of all dimensions in tensor shape.

.. index:: pair: function; itemsize
.. _doxid-structdlstreamer_1_1_tensor_info_1ab195722d64b8d02e3d73a791e6cc6101:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	size_t itemsize() const

Returns number bytes consumed by one element.

.. index:: pair: function; nbytes
.. _doxid-structdlstreamer_1_1_tensor_info_1a1dbae2ea0f0a20bd9f093b4453666c7b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	size_t nbytes() const

Return number bytes required to store tensor data in memory buffer.

.. index:: pair: function; is_contiguous
.. _doxid-structdlstreamer_1_1_tensor_info_1af4051b3f5ee7c113d9d9b39ca098067a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	bool is_contiguous() const

Return true if strides set to contiguous memory layout without padding.

