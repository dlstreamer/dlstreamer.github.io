.. index:: pair: class; gstgva::region_of_interest::RegionOfInterest
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest:

class gstgva::region_of_interest::RegionOfInterest
==================================================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents region of interest - object describing detection result (bounding box) and containing multiple Tensor objects (inference results) attached by multiple models. :ref:`More...<details-classgstgva_1_1region__of__interest_1_1_region_of_interest>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	class RegionOfInterest: public object {
	public:
		// methods
	
		def :ref:`rect<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a59bf32803e6692268c7c6128fc1e95d1>`(self self);
		def :ref:`normalized_rect<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a6feecd6670fe40bb89536cc3fc6f9e9d>`(self self);
		str :ref:`label<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a35612b6bcd681ffd388201cbdfdb5d1b>`(self self);
		float :ref:`confidence<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a04ce2b8860bed9ecdeb7bde6823e94a7>`(self self);
		int :ref:`object_id<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a71af5bbfd9aa73e456eb276e715ec799>`(self self);
		def :ref:`set_object_id<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1aa18caf2e18276971c8232241cf1216f4>`(self self, int object_id);
		def :ref:`tensors<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a046ba7fb121d48f07d9ed8af6c736258>`(self self);
		:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` :ref:`detection<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a2b6228cf390720f534c33d7d15d3f029>`(self self);
		int :ref:`label_id<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1af336f75b2857158690fae653cc18b60b>`(self self);
		:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` :ref:`add_tensor<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1af34160d6f6385fa1a3e326e154f667ef>`(self self, str name = "", :ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` tensor = None);
		VideoRegionOfInterestMeta :ref:`meta<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a7a3b0b57c0aac876304f5d1d093e43b4>`(self self);
		def :ref:`__init__<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a59fefcf6558f61f2ecc01ec866294d5e>`(self self, VideoRegionOfInterestMeta roi_meta);
		def :ref:`region_id<doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1acbd5d4152932e649b2f4a9bc54432dfe>`(self self);
	};
.. _details-classgstgva_1_1region__of__interest_1_1_region_of_interest:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents region of interest - object describing detection result (bounding box) and containing multiple Tensor objects (inference results) attached by multiple models.

For example, it can be region of interest with detected face and recognized age and sex of a person. It can be produced by a pipeline with gvadetect with detection model and two gvaclassify elements with two classification models. Such :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` will have bounding box coordinates filled and will have 3 Tensor objects attached - 1 Tensor object with detection result and 2 Tensor objects with classification results coming from 2 classifications

Methods
-------

.. index:: pair: function; rect
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a59bf32803e6692268c7c6128fc1e95d1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def rect(self self)

Get bounding box of the :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` as pixel coordinates in original image.



.. rubric:: Returns:

Bounding box coordinates of the :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`

.. index:: pair: function; normalized_rect
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a6feecd6670fe40bb89536cc3fc6f9e9d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def normalized_rect(self self)

Get bounding box of the :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` as normalized coordinates in the range [0, 1].



.. rubric:: Returns:

Bounding box coordinates of the :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`

.. index:: pair: function; label
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a35612b6bcd681ffd388201cbdfdb5d1b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	str label(self self)

Get class label of this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.



.. rubric:: Returns:

Class label of this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`

.. index:: pair: function; confidence
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a04ce2b8860bed9ecdeb7bde6823e94a7:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	float confidence(self self)

Get confidence from detection Tensor, last added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.



.. rubric:: Returns:

last added detection Tensor confidence if exists, otherwise None

.. index:: pair: function; object_id
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a71af5bbfd9aa73e456eb276e715ec799:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int object_id(self self)

Get object id.



.. rubric:: Returns:

object id as an int, None if failed to get

.. index:: pair: function; set_object_id
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1aa18caf2e18276971c8232241cf1216f4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def set_object_id(self self, int object_id)

Set object id.



.. rubric:: Returns:

None

.. index:: pair: function; tensors
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a046ba7fb121d48f07d9ed8af6c736258:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def tensors(self self)

Get all Tensor instances added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.



.. rubric:: Returns:

list of Tensor instances added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`

.. index:: pair: function; detection
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a2b6228cf390720f534c33d7d15d3f029:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` detection(self self)

Returns detection Tensor, last added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.

As any other Tensor, returned detection Tensor can contain arbitrary information. If you use :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` based on VideoRegionOfInterestMeta attached by gvadetect by default, then this Tensor will contain "label_id", "confidence", "x_min", "x_max", "y_min", "y_max" fields. If :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` doesn't have detection Tensor, it will be created in-place



.. rubric:: Returns:

detection Tensor, empty if there were no detection Tensor objects added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` when this method was called

.. index:: pair: function; label_id
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1af336f75b2857158690fae653cc18b60b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int label_id(self self)

Get label_id from detection Tensor, last added to this :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.



.. rubric:: Returns:

last added detection Tensor label_id if exists, otherwise None

.. index:: pair: function; add_tensor
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1af34160d6f6385fa1a3e326e154f667ef:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` add_tensor(self self, str name = "", :ref:`Tensor<doxid-classgstgva_1_1tensor_1_1_tensor>` tensor = None)

Add new Tensor (inference result) to the :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- Name for the tensor.

	*
		- tensor

		- (optional) Tensor object. This function does not take ownership of tensor passed, but only copies its contents



.. rubric:: Returns:

just created Tensor object, which can be filled with tensor information further

.. index:: pair: function; meta
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a7a3b0b57c0aac876304f5d1d093e43b4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	VideoRegionOfInterestMeta meta(self self)

Get VideoRegionOfInterestMeta containing bounding box information and tensors (inference results).

Tensors are represented as GstStructures added to GstVideoRegionOfInterestMeta.params



.. rubric:: Returns:

VideoRegionOfInterestMeta containing bounding box and tensors (inference results)

.. index:: pair: function; __init__
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1a59fefcf6558f61f2ecc01ec866294d5e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def __init__(self self, VideoRegionOfInterestMeta roi_meta)

Construct :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` instance from VideoRegionOfInterestMeta.

After this, :ref:`RegionOfInterest <doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest>` will obtain all tensors (detection & inference results) from VideoRegionOfInterestMeta



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- roi_meta

		- VideoRegionOfInterestMeta containing bounding box information and tensors

.. index:: pair: function; region_id
.. _doxid-classgstgva_1_1region__of__interest_1_1_region_of_interest_1acbd5d4152932e649b2f4a9bc54432dfe:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	def region_id(self self)

Get region ID.



.. rubric:: Returns:

Region id as an int. Can be a positive or negative integer, but never zero.

