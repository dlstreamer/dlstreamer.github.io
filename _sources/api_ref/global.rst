.. _global:
.. index:: pair: namespace; global

Global Namespace
================

.. toctree::
	:hidden:

	namespace_gstgva.rst
	enum_GVALayout.rst
	enum_GVAPrecision.rst
	struct_GstAnalyticsKeypoint.rst
	struct_GstAnalyticsKeypointPair.rst
	struct_GstGVAAudioEventMeta.rst
	struct__GstGVAJSONMeta.rst
	struct__GstGVATensorMeta.rst

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	// namespaces

	namespace :ref:`gstgva<doxid-namespacegstgva>`;
		namespace :ref:`gstgva::region_of_interest<doxid-namespacegstgva_1_1region__of__interest>`;
		namespace :ref:`gstgva::tensor<doxid-namespacegstgva_1_1tensor>`;
		namespace :ref:`gstgva::video_frame<doxid-namespacegstgva_1_1video__frame>`;

	// typedefs

	typedef typedefG_BEGIN_DECLS struct _GstAnalyticsMtd :ref:`GstAnalyticsKeypointMtd<doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409>`;
	typedef struct _GstAnalyticsMtd :ref:`GstAnalyticsKeypointSkeletonMtd<doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a>`;
	typedef struct _GstAnalyticsMtd :ref:`GstAnalyticsKeypointGroupMtd<doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8>`;
	typedef typedefG_BEGIN_DECLS struct :ref:`_GstGVAJSONMeta<doxid-struct___gst_g_v_a_j_s_o_n_meta>` :target:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`;
	typedef struct :ref:`_GstGVATensorMeta<doxid-struct___gst_g_v_a_tensor_meta>` :target:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`;
	typedef typedefG_BEGIN_DECLS struct _GstAnalyticsMtd :target:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`;

	// enums

	enum :ref:`GVALayout<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14ed>`;
	enum :ref:`GVAPrecision<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ce>`;

	// structs

	struct :ref:`GstAnalyticsKeypoint<doxid-struct_gst_analytics_keypoint>`;
	struct :ref:`GstAnalyticsKeypointPair<doxid-struct_gst_analytics_keypoint_pair>`;
	struct :ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`;
	struct :ref:`_GstGVAJSONMeta<doxid-struct___gst_g_v_a_j_s_o_n_meta>`;
	struct :ref:`_GstGVATensorMeta<doxid-struct___gst_g_v_a_tensor_meta>`;

	// global variables

	const int :target:`NEW_METADATA<doxid-objectdetectionmtdext_8h_1a09d15366318352adc2a6671508110b87>` = 0;

	// global functions

	GST_ANALYTICS_META_API GstAnalyticsMtdType :target:`gst_analytics_keypoint_mtd_get_mtd_type<doxid-gstanalyticskeypointsmtd_8h_1ac55d03113f30e5ce85b614c684acd824>`(void);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypoint_mtd_get<doxid-gstanalyticskeypointsmtd_8h_1ae4ebcca3f47b98cd29d881f2713a215a>`(
		const :ref:`GstAnalyticsKeypointMtd<doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409>`* handle,
		:ref:`GstAnalyticsKeypoint<doxid-struct_gst_analytics_keypoint>`* keypoint
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_add_keypoint_mtd<doxid-gstanalyticskeypointsmtd_8h_1a689e48dc24b1763f7a758d618eb9621d>`(
		GstAnalyticsRelationMeta* instance,
		const :ref:`GstAnalyticsKeypoint<doxid-struct_gst_analytics_keypoint>`* keypoint,
		:ref:`GstAnalyticsKeypointMtd<doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409>`* keypoint_mtd
	);

	GST_ANALYTICS_META_API GstAnalyticsMtdType :target:`gst_analytics_keypoint_skeleton_mtd_get_mtd_type<doxid-gstanalyticskeypointsmtd_8h_1a8566dfc7a7a0c08b230ec0dab18c93f1>`(void);
	GST_ANALYTICS_META_API gsize :target:`gst_analytics_keypoint_skeleton_mtd_get_count<doxid-gstanalyticskeypointsmtd_8h_1a3f779f64a2f4bfe5412cb3b45429ec6e>`(const :ref:`GstAnalyticsKeypointSkeletonMtd<doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a>`* handle);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypoint_skeleton_mtd_get<doxid-gstanalyticskeypointsmtd_8h_1ae4d3e4f6e7b5e824cdc94b6a7e5455a7>`(
		const :ref:`GstAnalyticsKeypointSkeletonMtd<doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a>`* handle,
		:ref:`GstAnalyticsKeypointPair<doxid-struct_gst_analytics_keypoint_pair>`* segment,
		gsize index
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_add_keypoint_skeleton_mtd<doxid-gstanalyticskeypointsmtd_8h_1a60be771e967f6c28b35af1cfe6589f2a>`(
		GstAnalyticsRelationMeta* instance,
		const gsize skeleton_count,
		const :ref:`GstAnalyticsKeypointPair<doxid-struct_gst_analytics_keypoint_pair>`* skeletons,
		:ref:`GstAnalyticsKeypointSkeletonMtd<doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a>`* keypoint_skeleton_mtd
	);

	GST_ANALYTICS_META_API GstAnalyticsMtdType :target:`gst_analytics_keypointgroup_mtd_get_mtd_type<doxid-gstanalyticskeypointsmtd_8h_1a6382f50ddf5173aabff3821bde52f8d3>`(void);
	GST_ANALYTICS_META_API gsize :target:`gst_analytics_keypointgroup_mtd_get_count<doxid-gstanalyticskeypointsmtd_8h_1a05a389ee9c146ed965f0ccd4ac5478e3>`(const :ref:`GstAnalyticsKeypointGroupMtd<doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8>`* handle);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypointgroup_mtd_get_keypoint_mtd<doxid-gstanalyticskeypointsmtd_8h_1a5a2ab28b5c78c17e76159209500e3c1d>`(
		const :ref:`GstAnalyticsKeypointGroupMtd<doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8>`* handle,
		:ref:`GstAnalyticsKeypointMtd<doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409>`* keypoint_mtd,
		gsize index
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_add_keypointgroup_mtd<doxid-gstanalyticskeypointsmtd_8h_1a8e2a86df6547df0751e7d6cdbdd91549>`(
		GstAnalyticsRelationMeta* instance,
		const gsize keypoint_count,
		const :ref:`GstAnalyticsKeypointMtd<doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409>`* keypoints,
		:ref:`GstAnalyticsKeypointGroupMtd<doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8>`* keypoints_mtd
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_set_keypointgroup_relations<doxid-gstanalyticskeypointsmtd_8h_1ab0976955b36df1a6b0bf9dbc87d2742f>`(
		GstAnalyticsRelationMeta* instance,
		:ref:`GstAnalyticsKeypointGroupMtd<doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8>`* keypoint_group,
		GstAnalyticsClsMtd* keypoint_names,
		:ref:`GstAnalyticsKeypointSkeletonMtd<doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a>`* keypoint_skeleton
	);

	DLS_EXPORT GType :target:`gst_gva_audio_event_meta_api_get_type<doxid-gva__audio__event__meta_8h_1ab900357c9549cd29850dae9d64764402>`(void);
	const GstMetaInfo* :target:`gst_gva_audio_event_meta_get_info<doxid-gva__audio__event__meta_8h_1ada019174d6ba549dd03bd53b456149f1>`(void);

	:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :target:`gst_gva_buffer_get_audio_event_meta_id<doxid-gva__audio__event__meta_8h_1a28911a7b18dd81195a62f99bfce3a677>`(
		GstBuffer* buffer,
		gint id
	);

	DLS_EXPORT :ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :target:`gst_gva_buffer_add_audio_event_meta<doxid-gva__audio__event__meta_8h_1a78e0412f62178b84daeff316440e1a7b>`(
		GstBuffer* buffer,
		const gchar* event_type,
		gulong start_timestamp,
		gulong end_timestamp
	);

	:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :target:`gst_gva_buffer_add_audio_event_meta_id<doxid-gva__audio__event__meta_8h_1a37a9125b4ca9dfddfabb5a75a0fd1672>`(
		GstBuffer* buffer,
		GQuark event_type,
		gulong start_timestamp,
		gulong end_timestamp
	);

	DLS_EXPORT void :target:`gst_gva_audio_event_meta_add_param<doxid-gva__audio__event__meta_8h_1a71b5f79e7958b04f6af52821525c5b5b>`(
		:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta,
		GstStructure* s
	);

	GstStructure* :target:`gst_gva_audio_event_meta_get_param<doxid-gva__audio__event__meta_8h_1ad70cb8cbce41685958c327888e1b1a4d>`(
		:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta,
		const gchar* name
	);

	DLS_EXPORT const GstMetaInfo* :ref:`gst_gva_json_meta_get_info<doxid-gva__json__meta_8h_1a5b3c0305d4b9ff9eebc366ca26d44977>`(void);
	DLS_EXPORT GType :ref:`gst_gva_json_meta_api_get_type<doxid-gva__json__meta_8h_1a681e2ec2e8c211ad0f03bd38a289c379>`(void);
	gchar* :ref:`get_json_message<doxid-gva__json__meta_8h_1aa545ce5192458c944e25cd7a420ba6c1>`(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta);
	void :ref:`set_json_message<doxid-gva__json__meta_8h_1a0ea9b77e35bd236b9d3e842764a970ae>`(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta, const gchar* message);
	const void* :ref:`gva_get_tensor_data<doxid-gva__tensor__meta_8h_1a10f40dae431beeca931a84d6e803df03>`(GstStructure* s, gsize* nbytes);
	DLS_EXPORT const GstMetaInfo* :ref:`gst_gva_tensor_meta_get_info<doxid-gva__tensor__meta_8h_1a41b460b5fc4511dd829c20935f3f6925>`(void);
	DLS_EXPORT GType :ref:`gst_gva_tensor_meta_api_get_type<doxid-gva__tensor__meta_8h_1a1a2fc0ce13c95f22aa6c10ec8e5430bf>`(void);

	:ref:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`* :ref:`find_tensor_meta<doxid-gva__tensor__meta_8h_1a8c412ce7685600f250c77914b95bdb1f>`(
		GstBuffer* buffer,
		const char* model_name,
		const char* output_layer
	);

	:ref:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`* :ref:`find_tensor_meta_ext<doxid-gva__tensor__meta_8h_1a9ffad4d93dc268c876678f6565a4745a>`(
		GstBuffer* buffer,
		const char* model_name,
		const char* output_layer,
		const char* element_id
	);

	GST_ANALYTICS_META_API DLS_EXPORT GstAnalyticsMtdType :target:`gst_analytics_od_ext_mtd_get_mtd_type<doxid-objectdetectionmtdext_8h_1a4886329247e380fd066386c3dfb48718>`(void);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_od_ext_mtd_get_rotation<doxid-objectdetectionmtdext_8h_1a047a2800e8a7cc4fc622853fe62e4d87>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* handle,
		gdouble* rotation
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_od_ext_mtd_get_class_id<doxid-objectdetectionmtdext_8h_1add9670b60a97abc285726f4ac9932fe5>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* handle,
		gint* class_id
	);

	GST_ANALYTICS_META_API DLS_EXPORT GList* :target:`gst_analytics_od_ext_mtd_get_params<doxid-objectdetectionmtdext_8h_1ab6c9927d18c3c8343f47b6bdd1f50f2f>`(const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* handle);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_od_ext_mtd_add_param<doxid-objectdetectionmtdext_8h_1a23091b6f3021ff737d1f213ea879b981>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* handle,
		GstStructure* s
	);

	GST_ANALYTICS_META_API GstStructure* :target:`gst_analytics_od_ext_mtd_get_param<doxid-objectdetectionmtdext_8h_1afc4a7c25eb94d858c72d32a8460d5959>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* handle,
		const gchar* name
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_add_od_ext_mtd<doxid-objectdetectionmtdext_8h_1a666abd130c6e98f2540e73701fb85fdf>`(
		GstAnalyticsRelationMeta* instance,
		gdouble rotation,
		gint class_id,
		:ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* od_ext_mtd
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_get_od_ext_mtd<doxid-objectdetectionmtdext_8h_1ae467ba19c4fcfe760e4070bd10dfab1f>`(
		GstAnalyticsRelationMeta* meta,
		gint an_meta_id,
		:ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a3cbd896154d2778ee22b2b4825379caf>`* rlt
	);

.. _details-global:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Typedefs
--------

.. index:: pair: typedef; GstAnalyticsKeypointMtd
.. _doxid-gstanalyticskeypointsmtd_8h_1ac8cf1e99cbe7388fafc4d24bb51a1409:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef typedefG_BEGIN_DECLS struct _GstAnalyticsMtd GstAnalyticsKeypointMtd

GstAnalyticsKeypointMtd: @id: Instance identifier. @meta: Instance of #GstAnalyticsRelationMeta where the analysis-metadata identified by @id is stored.

Handle to :ref:`GstAnalyticsKeypoint <doxid-struct_gst_analytics_keypoint>` data structure. This type is generally expected to be allocated on the stack.

Since: 1.26

.. index:: pair: typedef; GstAnalyticsKeypointSkeletonMtd
.. _doxid-gstanalyticskeypointsmtd_8h_1aa11d3893d074f85e896106b71bea4f9a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef struct _GstAnalyticsMtd GstAnalyticsKeypointSkeletonMtd

GstAnalyticsKeypointSkeletonMtd: @id: Instance identifier. @meta: Instance of #GstAnalyticsRelationMeta where the analysis-metadata identified by @id is stored.

Handle containing data required to use gst_analytics_keypoint_skeleton_mtd APIs. This type is generally expected to be allocated on the stack.

Since: 1.26

.. index:: pair: typedef; GstAnalyticsKeypointGroupMtd
.. _doxid-gstanalyticskeypointsmtd_8h_1ab379a79ec2fc34993cf77d7348538ed8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef struct _GstAnalyticsMtd GstAnalyticsKeypointGroupMtd

GstAnalyticsKeypointGroupMtd: @id: Instance identifier. @meta: Instance of #GstAnalyticsRelationMeta where the analysis-metadata identified by @id is stored.

Handle containing data required to use gst_analytics_keypointgroup_mtd APIs. This type is generally expected to be allocated on the stack.

Since: 1.26

Global Functions
----------------

.. index:: pair: function; gst_gva_json_meta_get_info
.. _doxid-gva__json__meta_8h_1a5b3c0305d4b9ff9eebc366ca26d44977:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	DLS_EXPORT const GstMetaInfo* gst_gva_json_meta_get_info(void)

This function registers, if needed, and returns GstMetaInfo for :ref:`_GstGVAJSONMeta <doxid-struct___gst_g_v_a_j_s_o_n_meta>`.



.. rubric:: Returns:

const GstMetaInfo* for registered type

.. index:: pair: function; gst_gva_json_meta_api_get_type
.. _doxid-gva__json__meta_8h_1a681e2ec2e8c211ad0f03bd38a289c379:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	DLS_EXPORT GType gst_gva_json_meta_api_get_type(void)

This function registers, if needed, and returns a GType for api "GstGVAJSONMetaAPI" and associate it with GVA_JSON_META_TAG tag.



.. rubric:: Returns:

GType type

.. index:: pair: function; get_json_message
.. _doxid-gva__json__meta_8h_1aa545ce5192458c944e25cd7a420ba6c1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	gchar* get_json_message(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta)

This function returns message field of :ref:`_GstGVAJSONMeta <doxid-struct___gst_g_v_a_j_s_o_n_meta>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- meta

		- _GstGVAJSONMeta* to retrieve message of



.. rubric:: Returns:

C-style string with message

.. index:: pair: function; set_json_message
.. _doxid-gva__json__meta_8h_1a0ea9b77e35bd236b9d3e842764a970ae:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	void set_json_message(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta, const gchar* message)

This function sets message field of :ref:`_GstGVAJSONMeta <doxid-struct___gst_g_v_a_j_s_o_n_meta>`.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- meta

		- _GstGVAJSONMeta* to set message

	*
		- message

		- message



.. rubric:: Returns:

void

.. index:: pair: function; gva_get_tensor_data
.. _doxid-gva__tensor__meta_8h_1a10f40dae431beeca931a84d6e803df03:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const void* gva_get_tensor_data(GstStructure* s, gsize* nbytes)

This function returns a pointer to the fixed array of tensor bytes.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- s

		- GstStructure* to get tensor from. It's assumed that tensor data is stored in "data_buffer" field

	*
		- nbytes

		- pointer to the location to store the number of bytes in returned array



.. rubric:: Returns:

void* to tensor data as bytes, NULL if s has no "data_buffer" field

.. index:: pair: function; gst_gva_tensor_meta_get_info
.. _doxid-gva__tensor__meta_8h_1a41b460b5fc4511dd829c20935f3f6925:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	DLS_EXPORT const GstMetaInfo* gst_gva_tensor_meta_get_info(void)

This function registers, if needed, and returns GstMetaInfo for :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>`.



.. rubric:: Returns:

GstMetaInfo* for registered type

.. index:: pair: function; gst_gva_tensor_meta_api_get_type
.. _doxid-gva__tensor__meta_8h_1a1a2fc0ce13c95f22aa6c10ec8e5430bf:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	DLS_EXPORT GType gst_gva_tensor_meta_api_get_type(void)

This function registers, if needed, and returns a GType for api "GstGVATensorMetaAPI" and associate it with GVA_TENSOR_META_TAG tag.



.. rubric:: Returns:

GType type

.. index:: pair: function; find_tensor_meta
.. _doxid-gva__tensor__meta_8h_1a8c412ce7685600f250c77914b95bdb1f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`* find_tensor_meta(
		GstBuffer* buffer,
		const char* model_name,
		const char* output_layer
	)

This function searches for first :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance that satisfies passed parameters.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* that is searched for metadata

	*
		- model_name

		- substring that should be in :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance's model_name

	*
		- output_layer

		- substring that should be in :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance's layer_name



.. rubric:: Returns:

GstGVATensorMeta* for found instance or NULL if none are found

.. index:: pair: function; find_tensor_meta_ext
.. _doxid-gva__tensor__meta_8h_1a9ffad4d93dc268c876678f6565a4745a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	:ref:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`* find_tensor_meta_ext(
		GstBuffer* buffer,
		const char* model_name,
		const char* output_layer,
		const char* element_id
	)

This function searches for first :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance that satisfies passed parameters.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- buffer

		- GstBuffer* that is searched for metadata

	*
		- model_name

		- substring that should be in :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance's model_name

	*
		- output_layer

		- substring that should be in :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance's layer_name

	*
		- element_id

		- element_id substring that should be in :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>` instance's element_id



.. rubric:: Returns:

GstGVATensorMeta* for found instance or NULL if none are found

