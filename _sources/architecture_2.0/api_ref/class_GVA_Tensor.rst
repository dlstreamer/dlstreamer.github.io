.. index:: pair: class; GVA::Tensor
.. _doxid-class_g_v_a_1_1_tensor:

class GVA::Tensor
=================

.. toctree::
	:hidden:

	enum_GVA_Tensor_Layout.rst
	enum_GVA_Tensor_Precision.rst

Overview
~~~~~~~~

This class represents tensor - map-like storage for inference result information, such as output blob description (output layer dims, layout, rank, precision, etc.), inference result in a raw and interpreted forms. :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is based on GstStructure and, in general, can contain arbitrary (user-defined) fields of simplest data types, like integers, floats & strings. :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` can contain raw inference result (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvainference in Gstreamer pipeline), detection result (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvadetect in Gstreamer pipeline and it's called detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`), or both raw & interpreted inference results (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvaclassify in Gstreamer pipeline). Tensors can be created and used on their own, or they can be created within :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` or :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instances. Usually, in Gstreamer pipeline with :ref:`GVA <doxid-namespace_g_v_a>` elements (gvadetect, gvainference, gvaclassify) :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects will be available for access and modification from :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` and :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instances. :ref:`More...<details-class_g_v_a_1_1_tensor>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <tensor.h>
	
	class Tensor {
	public:
		// enums
	
		enum :ref:`Layout<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>`;
		enum :ref:`Precision<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>`;

		// construction
	
		:ref:`Tensor<doxid-class_g_v_a_1_1_tensor_1a70f04bdac507b0ccba6fd0a24addad29>`(GstStructure* structure);

		// methods
	
		template <class T>
		const std::vector<T> :ref:`data<doxid-class_g_v_a_1_1_tensor_1ac61de94784df20b83e2b045b26b48506>`() const;
	
		void :ref:`set_data<doxid-class_g_v_a_1_1_tensor_1a22061b1190aa0952858e0bc2c2304019>`(const void* buffer, size_t size);
		std::vector<guint> :ref:`dims<doxid-class_g_v_a_1_1_tensor_1abea9f7ab67e6b2768e871b1ffa59c4e6>`() const;
		void :ref:`set_dims<doxid-class_g_v_a_1_1_tensor_1a062bb5088ed41318e9cb64cc5d873f04>`(const std::vector<guint>& dims);
		:ref:`Precision<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>` :ref:`precision<doxid-class_g_v_a_1_1_tensor_1afc914408f86c747a6ec12c4d3e28f61a>`() const;
		void :ref:`set_precision<doxid-class_g_v_a_1_1_tensor_1a42e3edca26cb702c94c24be2bf51a93f>`(const :ref:`Precision<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>` precision);
		:ref:`Layout<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>` :ref:`layout<doxid-class_g_v_a_1_1_tensor_1aef835f662ddf50b0973d00e34ea19793>`() const;
		void :ref:`set_layout<doxid-class_g_v_a_1_1_tensor_1ac09d3c20a2ff73376b78ca85097ea8ff>`(const :ref:`Layout<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>` layout);
		std::string :ref:`layer_name<doxid-class_g_v_a_1_1_tensor_1ac463c44557b69a233ee62a69de70e35e>`() const;
		void :ref:`set_layer_name<doxid-class_g_v_a_1_1_tensor_1a1d0c0dcd39a25bf48ded3ddc9d947076>`(const std::string& name);
		std::string :ref:`model_name<doxid-class_g_v_a_1_1_tensor_1a1e59cc380692947b6d2b1f4a2841d597>`() const;
		void :ref:`set_model_name<doxid-class_g_v_a_1_1_tensor_1af27065d033afdae29e24e4c82dd8822a>`(const std::string& name);
		std::string :ref:`format<doxid-class_g_v_a_1_1_tensor_1ae84bc122455ba1dc61d844c7d16df412>`() const;
		void :ref:`set_format<doxid-class_g_v_a_1_1_tensor_1a04b3aa0d4b4bd8ddc9e2c5f64f0aae06>`(const std::string& format);
		std::string :ref:`type<doxid-class_g_v_a_1_1_tensor_1a8eb9966dd42cb81474f6b3622746a778>`() const;
		void :ref:`set_type<doxid-class_g_v_a_1_1_tensor_1ad8442ccfb725eed25cd6117fd15f245a>`(const std::string& type);
		std::string :ref:`name<doxid-class_g_v_a_1_1_tensor_1ab4ff43a5debb89a3073204571d5c063a>`() const;
		void :ref:`set_name<doxid-class_g_v_a_1_1_tensor_1ad01bf81b1fb65f891197be588e54d29a>`(const std::string& name);
		double :ref:`confidence<doxid-class_g_v_a_1_1_tensor_1a131d6f95a68539ea0a9e22565e769d78>`() const;
		void :ref:`set_confidence<doxid-class_g_v_a_1_1_tensor_1a8d02450dce96741d5a22ba71b7b7e90f>`(const double confidence);
		std::string :ref:`label<doxid-class_g_v_a_1_1_tensor_1a81285ccb826dd979f0b77fa8361a7f06>`() const;
		void :ref:`set_label<doxid-class_g_v_a_1_1_tensor_1a249ddb89ab4abb3787d2836feccbc2c1>`(const std::string& label);
		std::vector<std::string> :ref:`fields<doxid-class_g_v_a_1_1_tensor_1aa45d665b0cace8a13c6b73f141585a55>`() const;
		bool :ref:`has_field<doxid-class_g_v_a_1_1_tensor_1a02af446bd566495a2d8915047445f717>`(const std::string& field_name) const;
	
		std::string :ref:`get_string<doxid-class_g_v_a_1_1_tensor_1a3dc174bc60e07621149318fed58fcb80>`(
			const std::string& field_name,
			const std::string& default_value = std::string()
		) const;
	
		int :ref:`get_int<doxid-class_g_v_a_1_1_tensor_1aa060cfe8ed40e586905868c0905b11e1>`(const std::string& field_name, int32_t default_value = 0) const;
		double :ref:`get_double<doxid-class_g_v_a_1_1_tensor_1ad06d2883a852b8713b7993f349616ee0>`(const std::string& field_name, double default_value = 0) const;
	
		template <typename T>
		std::vector<T> :ref:`get_vector<doxid-class_g_v_a_1_1_tensor_1a891cfbd45c26c1d9824c70c4b243a6b6>`(const char* field_name) const;
	
		template <typename T>
		void :ref:`set_vector<doxid-class_g_v_a_1_1_tensor_1a6f8ed9eaef0a76940eee1e2c977f996c>`(
			const char* field_name,
			const std::vector<T>& data
		);
	
		void :ref:`set_string<doxid-class_g_v_a_1_1_tensor_1a1cd955d556f2fd16df47d28e95b7b423>`(const std::string& field_name, const std::string& value);
		void :ref:`set_int<doxid-class_g_v_a_1_1_tensor_1a6bf5b624608bed60ea5b7edc5dddf61d>`(const std::string& field_name, int value);
		void :ref:`set_uint64<doxid-class_g_v_a_1_1_tensor_1a385209dd11378bd2ee37ef1a85f3eb86>`(const std::string& field_name, uint64_t value);
		void :ref:`set_double<doxid-class_g_v_a_1_1_tensor_1a899c7cd7ef6428a13a76f29a3869c730>`(const std::string& field_name, double value);
		void :ref:`set_bool<doxid-class_g_v_a_1_1_tensor_1acc6fef4506285743ac482547b0e1ff62>`(const std::string& field_name, bool value);
		std::string :ref:`precision_as_string<doxid-class_g_v_a_1_1_tensor_1aa33c11426d860d1562506b7bd8b4cabe>`() const;
		std::string :ref:`layout_as_string<doxid-class_g_v_a_1_1_tensor_1aeed9e5d0654804b6168b8e814806d69c>`() const;
		std::string :ref:`element_id<doxid-class_g_v_a_1_1_tensor_1a4ee8c5ca615cb3d864571946ffcc41d3>`() const;
		int :ref:`label_id<doxid-class_g_v_a_1_1_tensor_1aaa38a09854062816512e7d08e8c35498>`() const;
		bool :ref:`is_detection<doxid-class_g_v_a_1_1_tensor_1a28a71b8b0973df2df5707bb74b1588f7>`() const;
		GstStructure* :ref:`gst_structure<doxid-class_g_v_a_1_1_tensor_1a65270f22539aa9a422ab0bfa674cf214>`() const;
		std::string :ref:`to_string<doxid-class_g_v_a_1_1_tensor_1a0d856677b3c0f57bff510b5a26159599>`() const;
	
		bool :ref:`convert_to_meta<doxid-class_g_v_a_1_1_tensor_1a95ae5bee6254ab73644dc4ac107e4832>`(
			GstAnalyticsMtd* mtd,
			GstAnalyticsODMtd* od_mtd,
			GstAnalyticsRelationMeta* meta
		);
	
		static GstStructure* :target:`convert_to_tensor<doxid-class_g_v_a_1_1_tensor_1acb745d4f788b93a82de532a78ff76668>`(GstAnalyticsMtd mtd);
	};
.. _details-class_g_v_a_1_1_tensor:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents tensor - map-like storage for inference result information, such as output blob description (output layer dims, layout, rank, precision, etc.), inference result in a raw and interpreted forms. :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is based on GstStructure and, in general, can contain arbitrary (user-defined) fields of simplest data types, like integers, floats & strings. :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` can contain raw inference result (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvainference in Gstreamer pipeline), detection result (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvadetect in Gstreamer pipeline and it's called detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`), or both raw & interpreted inference results (such :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is produced by gvaclassify in Gstreamer pipeline). Tensors can be created and used on their own, or they can be created within :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` or :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instances. Usually, in Gstreamer pipeline with :ref:`GVA <doxid-namespace_g_v_a>` elements (gvadetect, gvainference, gvaclassify) :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` objects will be available for access and modification from :ref:`RegionOfInterest <doxid-class_g_v_a_1_1_region_of_interest>` and :ref:`VideoFrame <doxid-class_g_v_a_1_1_video_frame>` instances.

Construction
------------

.. index:: pair: function; Tensor
.. _doxid-class_g_v_a_1_1_tensor_1a70f04bdac507b0ccba6fd0a24addad29:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	Tensor(GstStructure* structure)

Construct :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance from GstStructure. :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` does not own structure, so if you use this constructor, free structure after :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` 's lifetime, if needed.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- structure

		- GstStructure to create :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance from.

Methods
-------

.. index:: pair: function; data
.. _doxid-class_g_v_a_1_1_tensor_1ac61de94784df20b83e2b045b26b48506:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	template <class T>
	const std::vector<T> data() const

Get raw inference output blob data.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- T

		- type to interpret blob data



.. rubric:: Returns:

vector of values of type T representing raw inference data, empty vector if data can't be read

.. index:: pair: function; set_data
.. _doxid-class_g_v_a_1_1_tensor_1a22061b1190aa0952858e0bc2c2304019:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_data(const void* buffer, size_t size)

Set raw data buffer as inference output data.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- with data element

	*
		- size

		- of data buffer in bytes

.. index:: pair: function; dims
.. _doxid-class_g_v_a_1_1_tensor_1abea9f7ab67e6b2768e871b1ffa59c4e6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<guint> dims() const

Get inference result blob dimensions info.



.. rubric:: Returns:

vector of dimensions. Empty vector if dims are not set

.. index:: pair: function; set_dims
.. _doxid-class_g_v_a_1_1_tensor_1a062bb5088ed41318e9cb64cc5d873f04:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_dims(const std::vector<guint>& dims)

Set inference result blob dimensions info.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- dims

		- vector of dimensions

.. index:: pair: function; precision
.. _doxid-class_g_v_a_1_1_tensor_1afc914408f86c747a6ec12c4d3e28f61a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Precision<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>` precision() const

Get inference output blob precision.



.. rubric:: Returns:

Enum Precision, :ref:`Precision::UNSPECIFIED <doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deeea1c04cc3823d476c3017238679a0fdf52>` if can't be read

.. index:: pair: function; set_precision
.. _doxid-class_g_v_a_1_1_tensor_1a42e3edca26cb702c94c24be2bf51a93f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_precision(const :ref:`Precision<doxid-class_g_v_a_1_1_tensor_1a1619104b4d017b07063ec70e5143deee>` precision)

Set inference output blob precision.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- precision

		- of inference data buffer

.. index:: pair: function; layout
.. _doxid-class_g_v_a_1_1_tensor_1aef835f662ddf50b0973d00e34ea19793:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`Layout<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>` layout() const

Get inference result blob layout.



.. rubric:: Returns:

Enum Layout, :ref:`Layout::ANY <doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650a8e1bde3c3d303163521522cf1d62f21f>` if can't be read

.. index:: pair: function; set_layout
.. _doxid-class_g_v_a_1_1_tensor_1ac09d3c20a2ff73376b78ca85097ea8ff:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_layout(const :ref:`Layout<doxid-class_g_v_a_1_1_tensor_1aefae220aa20aeeff872f7a9d7ccb2650>` layout)

Set layout of output blob precision.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- layout

		- of inference data buffer

.. index:: pair: function; layer_name
.. _doxid-class_g_v_a_1_1_tensor_1ac463c44557b69a233ee62a69de70e35e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string layer_name() const

Get inference result blob layer name.



.. rubric:: Returns:

layer name as a string, empty string if failed to get

.. index:: pair: function; set_layer_name
.. _doxid-class_g_v_a_1_1_tensor_1a1d0c0dcd39a25bf48ded3ddc9d947076:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_layer_name(const std::string& name)

Set name of output blob layer.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- of output blob layer

.. index:: pair: function; model_name
.. _doxid-class_g_v_a_1_1_tensor_1a1e59cc380692947b6d2b1f4a2841d597:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string model_name() const

Get model name which was used for inference.



.. rubric:: Returns:

model name as a string, empty string if failed to get

.. index:: pair: function; set_model_name
.. _doxid-class_g_v_a_1_1_tensor_1af27065d033afdae29e24e4c82dd8822a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_model_name(const std::string& name)

Set model name of output blob.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- of output blob model

.. index:: pair: function; format
.. _doxid-class_g_v_a_1_1_tensor_1ae84bc122455ba1dc61d844c7d16df412:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string format() const

Get data format as specified in model pre/post-processing json configuration.



.. rubric:: Returns:

format as a string, empty string if failed to get

.. index:: pair: function; set_format
.. _doxid-class_g_v_a_1_1_tensor_1a04b3aa0d4b4bd8ddc9e2c5f64f0aae06:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_format(const std::string& format)

Set inference output blob precision.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- format

		- of inference data buffer

.. index:: pair: function; type
.. _doxid-class_g_v_a_1_1_tensor_1a8eb9966dd42cb81474f6b3622746a778:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string type() const

Get tensor type as a string.



.. rubric:: Returns:

:ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance's type

.. index:: pair: function; set_type
.. _doxid-class_g_v_a_1_1_tensor_1ad8442ccfb725eed25cd6117fd15f245a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_type(const std::string& type)

Set tensor type as a string.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- type

		- of tensor data buffer

.. index:: pair: function; name
.. _doxid-class_g_v_a_1_1_tensor_1ab4ff43a5debb89a3073204571d5c063a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string name() const

Get tensor name as a string.



.. rubric:: Returns:

:ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance's name

.. index:: pair: function; set_name
.. _doxid-class_g_v_a_1_1_tensor_1ad01bf81b1fb65f891197be588e54d29a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_name(const std::string& name)

Set :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance's name.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- of tensor instance

.. index:: pair: function; confidence
.. _doxid-class_g_v_a_1_1_tensor_1a131d6f95a68539ea0a9e22565e769d78:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	double confidence() const

Get confidence of detection or classification result extracted from the tensor.



.. rubric:: Returns:

confidence of inference result as a double, 0 if failed to get

.. index:: pair: function; set_confidence
.. _doxid-class_g_v_a_1_1_tensor_1a8d02450dce96741d5a22ba71b7b7e90f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_confidence(const double confidence)

Set confidence of detection or classification result.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- confidence

		- of inference result

.. index:: pair: function; label
.. _doxid-class_g_v_a_1_1_tensor_1a81285ccb826dd979f0b77fa8361a7f06:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string label() const

Get label. This label is set for :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instances produced by gvaclassify element. It will throw an exception if called for detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`. To get detection class label, use :ref:`RegionOfInterest::label <doxid-class_g_v_a_1_1_region_of_interest_1a1e70434428a6b20dbd35be7837761ffa>`.



.. rubric:: Returns:

label as a string, empty string if failed to get

.. index:: pair: function; set_label
.. _doxid-class_g_v_a_1_1_tensor_1a249ddb89ab4abb3787d2836feccbc2c1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_label(const std::string& label)

Set label. It will throw an exception if called for detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- label

		- label name as a string

.. index:: pair: function; fields
.. _doxid-class_g_v_a_1_1_tensor_1aa45d665b0cace8a13c6b73f141585a55:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::vector<std::string> fields() const

Get vector of fields contained in :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance.



.. rubric:: Returns:

vector of fields contained in :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance

.. index:: pair: function; has_field
.. _doxid-class_g_v_a_1_1_tensor_1a02af446bd566495a2d8915047445f717:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	bool has_field(const std::string& field_name) const

Check if :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` instance has field.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name



.. rubric:: Returns:

True if field with this name is found, False otherwise

.. index:: pair: function; get_string
.. _doxid-class_g_v_a_1_1_tensor_1a3dc174bc60e07621149318fed58fcb80:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string get_string(
		const std::string& field_name,
		const std::string& default_value = std::string()
	) const

Get string contained in value stored at field_name.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- default_value

		- default value



.. rubric:: Returns:

string value stored at field_name if field_name is found and contains a string, default_value string otherwise

.. index:: pair: function; get_int
.. _doxid-class_g_v_a_1_1_tensor_1aa060cfe8ed40e586905868c0905b11e1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int get_int(const std::string& field_name, int32_t default_value = 0) const

Get int contained in value stored at field_name.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- default_value

		- default value



.. rubric:: Returns:

int value stored at field_name if field_name is found and contains an int, default_value otherwise

.. index:: pair: function; get_double
.. _doxid-class_g_v_a_1_1_tensor_1ad06d2883a852b8713b7993f349616ee0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	double get_double(const std::string& field_name, double default_value = 0) const

Get double contained in value stored at field_name.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- default_value

		- default value



.. rubric:: Returns:

double value stored at field_name if field_name is found and contains an double, default_value otherwise

.. index:: pair: function; get_vector
.. _doxid-class_g_v_a_1_1_tensor_1a891cfbd45c26c1d9824c70c4b243a6b6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	template <typename T>
	std::vector<T> get_vector(const char* field_name) const

Get vector stored as GST_TYPE_ARRAY field.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- name of GST_TYPE_ARRAY field to get



.. rubric:: Returns:

vector with data of type T

.. index:: pair: function; set_vector
.. _doxid-class_g_v_a_1_1_tensor_1a6f8ed9eaef0a76940eee1e2c977f996c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	template <typename T>
	void set_vector(
		const char* field_name,
		const std::vector<T>& data
	)

Set vector as GST_TYPE_ARRAY field.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- name of GST_TYPE_ARRAY field to set

	*
		- data

		- vector to set

.. index:: pair: function; set_string
.. _doxid-class_g_v_a_1_1_tensor_1a1cd955d556f2fd16df47d28e95b7b423:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_string(const std::string& field_name, const std::string& value)

Set field_name with string value.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- value

		- value to set

.. index:: pair: function; set_int
.. _doxid-class_g_v_a_1_1_tensor_1a6bf5b624608bed60ea5b7edc5dddf61d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_int(const std::string& field_name, int value)

Set field_name with int value.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- value

		- value to set

.. index:: pair: function; set_uint64
.. _doxid-class_g_v_a_1_1_tensor_1a385209dd11378bd2ee37ef1a85f3eb86:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_uint64(const std::string& field_name, uint64_t value)

Set field_name with uint64 value.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- value

		- value to set

.. index:: pair: function; set_double
.. _doxid-class_g_v_a_1_1_tensor_1a899c7cd7ef6428a13a76f29a3869c730:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_double(const std::string& field_name, double value)

Set field_name with double value.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- value

		- value to set

.. index:: pair: function; set_bool
.. _doxid-class_g_v_a_1_1_tensor_1acc6fef4506285743ac482547b0e1ff62:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_bool(const std::string& field_name, bool value)

Set field_name with bool value.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- field_name

		- field name

	*
		- value

		- value to set

.. index:: pair: function; precision_as_string
.. _doxid-class_g_v_a_1_1_tensor_1aa33c11426d860d1562506b7bd8b4cabe:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string precision_as_string() const

Get inference result blob precision as a string.



.. rubric:: Returns:

precision as a string, "ANY" if can't be read

.. index:: pair: function; layout_as_string
.. _doxid-class_g_v_a_1_1_tensor_1aeed9e5d0654804b6168b8e814806d69c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string layout_as_string() const

Get inference result blob layout as a string.



.. rubric:: Returns:

layout as a string, "ANY" if can't be read

.. index:: pair: function; element_id
.. _doxid-class_g_v_a_1_1_tensor_1a4ee8c5ca615cb3d864571946ffcc41d3:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string element_id() const

Get inference-id property value of :ref:`GVA <doxid-namespace_g_v_a>` element from which this :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` came.



.. rubric:: Returns:

inference-id property value of :ref:`GVA <doxid-namespace_g_v_a>` element from which this :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` came, empty string if failed to get

.. index:: pair: function; label_id
.. _doxid-class_g_v_a_1_1_tensor_1aaa38a09854062816512e7d08e8c35498:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	int label_id() const

Get label id.



.. rubric:: Returns:

label id as an int, 0 if failed to get

.. index:: pair: function; is_detection
.. _doxid-class_g_v_a_1_1_tensor_1a28a71b8b0973df2df5707bb74b1588f7:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	bool is_detection() const

Check if this :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` is detection :ref:`Tensor <doxid-class_g_v_a_1_1_tensor>` (contains detection results)



.. rubric:: Returns:

True if tensor contains detection results, False otherwise

.. index:: pair: function; gst_structure
.. _doxid-class_g_v_a_1_1_tensor_1a65270f22539aa9a422ab0bfa674cf214:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GstStructure* gst_structure() const

Get ptr to underlying GstStructure.



.. rubric:: Returns:

ptr to underlying GstStructure

.. index:: pair: function; to_string
.. _doxid-class_g_v_a_1_1_tensor_1a0d856677b3c0f57bff510b5a26159599:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	std::string to_string() const

Returns a string representation of the underlying GstStructure.



.. rubric:: Returns:

String with GstStructure contents.

.. index:: pair: function; convert_to_meta
.. _doxid-class_g_v_a_1_1_tensor_1a95ae5bee6254ab73644dc4ac107e4832:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	bool convert_to_meta(
		GstAnalyticsMtd* mtd,
		GstAnalyticsODMtd* od_mtd,
		GstAnalyticsRelationMeta* meta
	)

Convert tensor to GST analytic metadata.



.. rubric:: Returns:

if conversion succesfull, 'mtd' is a handle to created metadata

