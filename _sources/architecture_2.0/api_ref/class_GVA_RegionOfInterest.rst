.. index:: pair: class; GVA::RegionOfInterest
.. _doxid-class_g_v_a_1_1_region_of_interest:

class GVA::RegionOfInterest
===========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents region of interest - object describing detection result (bounding box) and containing multiple :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results) attached by multiple models. For example, it can be region of interest with detected face and recognized age and sex of a person. It can be produced by a pipeline with gvadetect with detection model and two gvaclassify elements with two classification models. Such :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` will have bounding box coordinates filled and will have 3 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached - 1 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object with detection result and 2 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects with classification results coming from 2 classifications. :ref:`More...<details-class_g_v_a_1_1_region_of_interest>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <region_of_interest.h>
	
	class RegionOfInterest {
	public:
		// construction
	
		:ref:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest_1a68e47be95f3d19b9537fa1b6db230ab9>`(GstVideoRegionOfInterestMeta* meta);
		:target:`RegionOfInterest<doxid-class_g_v_a_1_1_region_of_interest_1a0b8de147d9ac722fcc06ef0b70e56296>`(GstAnalyticsODMtd od_meta, :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>` od_ext_meta);

		// methods
	
		:ref:`Rect<doxid-struct_g_v_a_1_1_rect>`<uint32_t> :ref:`rect<doxid-class_g_v_a_1_1_region_of_interest_1a2556d1b0a7aa98d36eea9979f8c316bc>`() const;
		:ref:`Rect<doxid-struct_g_v_a_1_1_rect>`<double> :ref:`normalized_rect<doxid-class_g_v_a_1_1_region_of_interest_1a72d3986623d95742855be5e0c46ae544>`();
		double :ref:`rotation<doxid-class_g_v_a_1_1_region_of_interest_1a8fd47982b2c1d54e97e3700e90236985>`() const;
		std::string :ref:`label<doxid-class_g_v_a_1_1_region_of_interest_1a1e70434428a6b20dbd35be7837761ffa>`() const;
		double :ref:`confidence<doxid-class_g_v_a_1_1_region_of_interest_1acfaa4092998146914af651a094edad6c>`() const;
		int32_t :ref:`object_id<doxid-class_g_v_a_1_1_region_of_interest_1a4846b8816a96a08286ec25fa2a61356f>`() const;
		std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> :ref:`tensors<doxid-class_g_v_a_1_1_region_of_interest_1a383150acbf54733342df8aaaab6f650c>`() const;
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`add_tensor<doxid-class_g_v_a_1_1_region_of_interest_1aba2238d0ce000d31ae00a4ca495cca88>`(const std::string& name);
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` :ref:`detection<doxid-class_g_v_a_1_1_region_of_interest_1aa3360d1e9ffd9f4921905cfc756d2f4a>`();
		int :ref:`label_id<doxid-class_g_v_a_1_1_region_of_interest_1a7d226e7a6907606bb5b4bc3a352bea44>`() const;
		int :ref:`region_id<doxid-class_g_v_a_1_1_region_of_interest_1a91c9985c5999559f0d3070ec074e775b>`();
		void :ref:`set_label<doxid-class_g_v_a_1_1_region_of_interest_1a727e82a6852257125c1b33c753688e96>`(std::string label);
		void :ref:`set_object_id<doxid-class_g_v_a_1_1_region_of_interest_1aacf218f09e39c695011807f890242c63>`(int32_t id);
		GList* :target:`get_params<doxid-class_g_v_a_1_1_region_of_interest_1a48d24ec0ee33f12a483d1f7b82afde04>`() const;
		GstStructure* :target:`get_param<doxid-class_g_v_a_1_1_region_of_interest_1ab7e8f4e7dc93b48559b2629c00fd662b>`(const char* name) const;
		void :target:`add_param<doxid-class_g_v_a_1_1_region_of_interest_1a5855eb0e5af310ccacfaa8fc54818a46>`(GstStructure* s);
		GstVideoRegionOfInterestMeta* :ref:`_meta<doxid-class_g_v_a_1_1_region_of_interest_1ae48caa3aabb78046ecb676bd6f8d59ef>`() const;
	};
.. _details-class_g_v_a_1_1_region_of_interest:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents region of interest - object describing detection result (bounding box) and containing multiple :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects (inference results) attached by multiple models. For example, it can be region of interest with detected face and recognized age and sex of a person. It can be produced by a pipeline with gvadetect with detection model and two gvaclassify elements with two classification models. Such :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` will have bounding box coordinates filled and will have 3 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects attached - 1 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object with detection result and 2 :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects with classification results coming from 2 classifications.

Construction
------------

.. index:: pair: function; RegionOfInterest
.. _doxid-class_g_v_a_1_1_region_of_interest_1a68e47be95f3d19b9537fa1b6db230ab9:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	RegionOfInterest(GstVideoRegionOfInterestMeta* meta)

Construct :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` instance from GstVideoRegionOfInterestMeta. After this, :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` will obtain all tensors (detection & inference results) from GstVideoRegionOfInterestMeta.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- meta

		- GstVideoRegionOfInterestMeta containing bounding box information and tensors

Methods
-------

.. index:: pair: function; rect
.. _doxid-class_g_v_a_1_1_region_of_interest_1a2556d1b0a7aa98d36eea9979f8c316bc:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Rect<doxid-struct_g_v_a_1_1_rect>`<uint32_t> rect() const

Get bounding box of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` as pixel coordinates in original image.



.. rubric:: Returns:

Bounding box coordinates of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`

.. index:: pair: function; normalized_rect
.. _doxid-class_g_v_a_1_1_region_of_interest_1a72d3986623d95742855be5e0c46ae544:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Rect<doxid-struct_g_v_a_1_1_rect>`<double> normalized_rect()

Get bounding box of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` as normalized coordinates in the range [0, 1].



.. rubric:: Returns:

Bounding box coordinates of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`

.. index:: pair: function; rotation
.. _doxid-class_g_v_a_1_1_region_of_interest_1a8fd47982b2c1d54e97e3700e90236985:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	double rotation() const

Get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` bounding box rotation.



.. rubric:: Returns:

Bounding box rotation of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`

.. index:: pair: function; label
.. _doxid-class_g_v_a_1_1_region_of_interest_1a1e70434428a6b20dbd35be7837761ffa:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string label() const

Get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` label.



.. rubric:: Returns:

:ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` label

.. index:: pair: function; confidence
.. _doxid-class_g_v_a_1_1_region_of_interest_1acfaa4092998146914af651a094edad6c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	double confidence() const

Get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` detection confidence (set by gvadetect)



.. rubric:: Returns:

last added detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` confidence if exists, otherwise 0.0

.. index:: pair: function; object_id
.. _doxid-class_g_v_a_1_1_region_of_interest_1a4846b8816a96a08286ec25fa2a61356f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int32_t object_id() const

Get unique id of the :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`. The id typically created by gvatrack element.



.. rubric:: Returns:

Unique id, or zero value if not found

.. index:: pair: function; tensors
.. _doxid-class_g_v_a_1_1_region_of_interest_1a383150acbf54733342df8aaaab6f650c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>`> tensors() const

Get all :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instances added to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`.



.. rubric:: Returns:

vector of :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instances added to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`

.. index:: pair: function; add_tensor
.. _doxid-class_g_v_a_1_1_region_of_interest_1aba2238d0ce000d31ae00a4ca495cca88:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` add_tensor(const std::string& name)

Add new tensor (inference result) to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` with name set. To add detection tensor, set name to "detection".



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- name for the tensor. If name is set to "detection", detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` will be created and set for this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`



.. rubric:: Returns:

just created :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` object, which can be filled with tensor information further

.. index:: pair: function; detection
.. _doxid-class_g_v_a_1_1_region_of_interest_1aa3360d1e9ffd9f4921905cfc756d2f4a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Tensor<doxid-class_g_v_a_1_1_tensor>` detection()

Returns detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, last added to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`. As any other :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, returned detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` can contain arbitrary information. If you use :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` based on GstVideoRegionOfInterestMeta attached by gvadetect by default, then this :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` will contain "label_id", "confidence", "x_min", "x_max", "y_min", "y_max" fields. If :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` doesn't have detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, it will be created in-place.



.. rubric:: Returns:

detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, empty if there were no detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects added to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` when this method was called

.. index:: pair: function; label_id
.. _doxid-class_g_v_a_1_1_region_of_interest_1a7d226e7a6907606bb5b4bc3a352bea44:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int label_id() const

Get label_id from detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`, last added to this :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>`.



.. rubric:: Returns:

last added detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` label_id if exists, otherwise 0

.. index:: pair: function; region_id
.. _doxid-class_g_v_a_1_1_region_of_interest_1a91c9985c5999559f0d3070ec074e775b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int region_id()

Access :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` ID Use this method to get :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` ID. ID is generated with "GVA::VideoFrame::add_region()" call. Region ID can be a positive or negative integer, but never zero.



.. rubric:: Returns:

ID field value

.. index:: pair: function; set_label
.. _doxid-class_g_v_a_1_1_region_of_interest_1a727e82a6852257125c1b33c753688e96:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_label(std::string label)

Set :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` label.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- label

		- Label to set

.. index:: pair: function; set_object_id
.. _doxid-class_g_v_a_1_1_region_of_interest_1aacf218f09e39c695011807f890242c63:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_object_id(int32_t id)

Set object ID.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- id

		- ID to set

.. index:: pair: function; _meta
.. _doxid-class_g_v_a_1_1_region_of_interest_1ae48caa3aabb78046ecb676bd6f8d59ef:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstVideoRegionOfInterestMeta* _meta() const

Internal function, don't use or use with caution.



.. rubric:: Returns:

pointer to underlying GstVideoRegionOfInterestMeta

