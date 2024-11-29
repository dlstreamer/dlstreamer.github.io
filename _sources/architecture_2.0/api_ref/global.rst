.. _global:
.. index:: pair: namespace; global

Global Namespace
================

.. toctree::
	:hidden:

	namespace_GVA.rst
	namespace_dlstreamer.rst
	enum_GVALayout.rst
	enum_GVAPrecision.rst
	enum_GstAnalyticsKeypointDimensions.rst
	struct_GstGVAAudioEventMeta.rst
	struct_GstKeypointPair.rst
	struct__GstAnalyticsODExtMtdData.rst
	struct__GstGVAJSONMeta.rst
	struct__GstGVATensorMeta.rst

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	// namespaces

	namespace :ref:`GVA<doxid-namespace_g_v_a>`;
	namespace :ref:`dlstreamer<doxid-namespacedlstreamer>`;
		namespace :ref:`dlstreamer::detail<doxid-namespacedlstreamer_1_1detail>`;
		namespace :ref:`dlstreamer::param<doxid-namespacedlstreamer_1_1param>`;
		namespace :ref:`dlstreamer::tensor<doxid-namespacedlstreamer_1_1tensor>`;
			namespace :ref:`dlstreamer::tensor::key<doxid-namespacedlstreamer_1_1tensor_1_1key>`;

	// typedefs

	typedef struct _cl_mem* :target:`cl_mem<doxid-opencl_2tensor_8h_1af2141916ad9655073b9810d7bc71494d>`;
	typedef typedefG_BEGIN_DECLS struct _GstAnalyticsMtd :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`;
	typedef typedefG_BEGIN_DECLS struct :ref:`_GstGVAJSONMeta<doxid-struct___gst_g_v_a_j_s_o_n_meta>` :target:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`;
	typedef struct :ref:`_GstGVATensorMeta<doxid-struct___gst_g_v_a_tensor_meta>` :target:`GstGVATensorMeta<doxid-gva__tensor__meta_8h_1a038ecf5fdabb0acf1f2053800ba16d62>`;
	typedef struct _GstAnalyticsMtd :target:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`;
	typedef struct :ref:`_GstAnalyticsODExtMtdData<doxid-struct___gst_analytics_o_d_ext_mtd_data>` :target:`GstAnalyticsODExtMtdData<doxid-objectdetectionmtdext_8h_1ada240bd3f645b92f904b600bc6bee4d2>`;

	// enums

	enum :ref:`GVALayout<doxid-gva__tensor__meta_8h_1a2d0113c46cec570b215b893571ab14ed>`;
	enum :ref:`GVAPrecision<doxid-gva__tensor__meta_8h_1ac26bbefa1eda84e0a4b888d51d2795ce>`;
	enum :ref:`GstAnalyticsKeypointDimensions<doxid-gstanalyticskeypointsmtd_8h_1a9034de0e92b489c3805199eb05a434df>`;

	// structs

	struct :ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`;
	struct :ref:`GstKeypointPair<doxid-struct_gst_keypoint_pair>`;
	struct :ref:`_GstAnalyticsODExtMtdData<doxid-struct___gst_analytics_o_d_ext_mtd_data>`;
	struct :ref:`_GstGVAJSONMeta<doxid-struct___gst_g_v_a_j_s_o_n_meta>`;
	struct :ref:`_GstGVATensorMeta<doxid-struct___gst_g_v_a_tensor_meta>`;

	// global variables

	const :ref:`dlstreamer::ElementDesc<doxid-structdlstreamer_1_1_element_desc>`* :target:`dlstreamer_elements<doxid-element_8h_1a987bf5e60e7e63da522cd55828febf58>`[];
	const bool :target:`NEW_METADATA<doxid-objectdetectionmtdext_8h_1a6efe41ea3b1fe01677f869edc79dca48>` = false;
	const GstAnalyticsMtdImpl :target:`od_ext_impl<doxid-objectdetectionmtdext_8h_1a3560695668336b9a042b81ec4880914d>` = {"object-detection-extended", NULL, {NULL}};

	// global functions

	GST_ANALYTICS_META_API GstAnalyticsMtdType :target:`gst_analytics_keypoints_mtd_get_mtd_type<doxid-gstanalyticskeypointsmtd_8h_1a5688ba87dcd0136b3c61e60e9b41e1a6>`(void);
	GST_ANALYTICS_META_API gsize :target:`gst_analytics_keypoints_mtd_get_count<doxid-gstanalyticskeypointsmtd_8h_1a3acbe6dfc99b789be84659a8baf2d8db>`(const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle);
	GST_ANALYTICS_META_API :ref:`GstAnalyticsKeypointDimensions<doxid-gstanalyticskeypointsmtd_8h_1a9034de0e92b489c3805199eb05a434df>` :target:`gst_analytics_keypoints_mtd_get_dimension<doxid-gstanalyticskeypointsmtd_8h_1a88bff3d8ee03caa1209688168e1e7042>`(const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle);
	GST_ANALYTICS_META_API gsize :target:`gst_analytics_keypoints_mtd_get_confidence_count<doxid-gstanalyticskeypointsmtd_8h_1af20f328cd1ed07f1469a2e788037b28a>`(const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle);
	GST_ANALYTICS_META_API gsize :target:`gst_analytics_keypoints_mtd_get_skeleton_count<doxid-gstanalyticskeypointsmtd_8h_1a94e1da49995eabb555f698d57ee26f60>`(const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypoints_mtd_get_position<doxid-gstanalyticskeypointsmtd_8h_1a2ce9b7b78426f2c721f588abafcbbb3d>`(
		const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle,
		gfloat* position,
		gsize index
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypoints_mtd_get_confidence<doxid-gstanalyticskeypointsmtd_8h_1a7a0ef1cbadbd7b8c694a0f5deeb4a452>`(
		const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle,
		gfloat* confidence,
		gsize index
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_keypoints_mtd_get_skeleton<doxid-gstanalyticskeypointsmtd_8h_1ab0715d81a5f3861546d83a970b9f28dd>`(
		const :ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* handle,
		:ref:`GstKeypointPair<doxid-struct_gst_keypoint_pair>`* skeleton,
		gsize index
	);

	GST_ANALYTICS_META_API gboolean :target:`gst_analytics_relation_meta_add_keypoints_mtd<doxid-gstanalyticskeypointsmtd_8h_1ae59799f7d85c4489a2a49e53c6ee0fba>`(
		GstAnalyticsRelationMeta* instance,
		const gsize keypoint_count,
		const :ref:`GstAnalyticsKeypointDimensions<doxid-gstanalyticskeypointsmtd_8h_1a9034de0e92b489c3805199eb05a434df>` keypoint_dimensions,
		const gfloat* positions,
		const gfloat* confidences,
		const gsize skeleton_count,
		const :ref:`GstKeypointPair<doxid-struct_gst_keypoint_pair>`* skeletons,
		:ref:`GstAnalyticsKeypointsMtd<doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d>`* keypoint_mtd
	);

	GType :target:`gst_gva_audio_event_meta_api_get_type<doxid-gva__audio__event__meta_8h_1abbda3842d56b2d1be936c56fc10b5fe4>`(void);
	const GstMetaInfo* :target:`gst_gva_audio_event_meta_get_info<doxid-gva__audio__event__meta_8h_1ada019174d6ba549dd03bd53b456149f1>`(void);

	:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :target:`gst_gva_buffer_get_audio_event_meta_id<doxid-gva__audio__event__meta_8h_1a28911a7b18dd81195a62f99bfce3a677>`(
		GstBuffer* buffer,
		gint id
	);

	:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* :target:`gst_gva_buffer_add_audio_event_meta<doxid-gva__audio__event__meta_8h_1a4afcfba36998cd584614490ecf310f75>`(
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

	void :target:`gst_gva_audio_event_meta_add_param<doxid-gva__audio__event__meta_8h_1ab2ac8cd76f8f0a52f344f80921903f20>`(
		:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta,
		GstStructure* s
	);

	GstStructure* :target:`gst_gva_audio_event_meta_get_param<doxid-gva__audio__event__meta_8h_1ad70cb8cbce41685958c327888e1b1a4d>`(
		:ref:`GstGVAAudioEventMeta<doxid-struct_gst_g_v_a_audio_event_meta>`* meta,
		const gchar* name
	);

	const GstMetaInfo* :ref:`gst_gva_json_meta_get_info<doxid-gva__json__meta_8h_1aa3e2cbd81b77b33be3a69a11c190cb57>`(void);
	GType :ref:`gst_gva_json_meta_api_get_type<doxid-gva__json__meta_8h_1a4136c51ca9905bc6da7a3536ca957899>`(void);
	gchar* :ref:`get_json_message<doxid-gva__json__meta_8h_1aa545ce5192458c944e25cd7a420ba6c1>`(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta);
	void :ref:`set_json_message<doxid-gva__json__meta_8h_1a0ea9b77e35bd236b9d3e842764a970ae>`(:ref:`GstGVAJSONMeta<doxid-gva__json__meta_8h_1a64a17a6fb82826c3a7159e71c9449a54>`* meta, const gchar* message);
	const void* :ref:`gva_get_tensor_data<doxid-gva__tensor__meta_8h_1a10f40dae431beeca931a84d6e803df03>`(GstStructure* s, gsize* nbytes);
	const GstMetaInfo* :ref:`gst_gva_tensor_meta_get_info<doxid-gva__tensor__meta_8h_1a09753594569dbadb68669cdddf5bdad1>`(void);
	GType :ref:`gst_gva_tensor_meta_api_get_type<doxid-gva__tensor__meta_8h_1ac5b45e42b95ae7bb4bd51711551fd3c1>`(void);

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

	GST_EXPORT gboolean :target:`register_element_gst_plugin<doxid-plugin_8h_1a778af1fb568fd01400c33e1bc59b957f>`(
		const :ref:`dlstreamer::ElementDesc<doxid-structdlstreamer_1_1_element_desc>`* element,
		GstPlugin* plugin
	);

	GST_EXPORT gboolean :target:`register_elements_gst_plugin<doxid-plugin_8h_1a647fb58a58356734d096474386eb7c1d>`(
		const :ref:`dlstreamer::ElementDesc<doxid-structdlstreamer_1_1_element_desc>`** elements,
		GstPlugin* plugin
	);

	GstAnalyticsMtdType :target:`gst_analytics_od_ext_mtd_get_mtd_type<doxid-objectdetectionmtdext_8h_1ae72a232419a7c2fbe1dbfcbe14a516bd>`(void);

	gboolean :target:`gst_analytics_od_ext_mtd_get_rotation<doxid-objectdetectionmtdext_8h_1a679f9449a4d9edc30f13b9b9d9cc42fa>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* handle,
		gdouble* rotation
	);

	gboolean :target:`gst_analytics_od_ext_mtd_get_class_id<doxid-objectdetectionmtdext_8h_1afdb32f39f2d632080f0f140fca5a0b2a>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* handle,
		gint* class_id
	);

	GList* :target:`gst_analytics_od_ext_mtd_get_params<doxid-objectdetectionmtdext_8h_1a28ac3f309de5e42d328f5906a63124f9>`(const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* handle);

	gboolean :target:`gst_analytics_od_ext_mtd_add_param<doxid-objectdetectionmtdext_8h_1abeba362286a1d00c3c9214166afeac4e>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* handle,
		GstStructure* s
	);

	GstStructure* :target:`gst_analytics_od_ext_mtd_get_param<doxid-objectdetectionmtdext_8h_1ab59d31eddaacd1157fbf6721df716d7f>`(
		const :ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* handle,
		const gchar* name
	);

	gboolean :target:`gst_analytics_relation_meta_add_od_ext_mtd<doxid-objectdetectionmtdext_8h_1a7586af35981094c1bf10ecb97971526c>`(
		GstAnalyticsRelationMeta* instance,
		gdouble rotation,
		gint class_id,
		:ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* od_ext_mtd
	);

	gboolean :target:`gst_analytics_relation_meta_get_od_ext_mtd<doxid-objectdetectionmtdext_8h_1a56f9f71dd39a22ceffdbbf07aa73333e>`(
		GstAnalyticsRelationMeta* meta,
		gint an_meta_id,
		:ref:`GstAnalyticsODExtMtd<doxid-objectdetectionmtdext_8h_1a0c8b8479b3989230d7585990ead9e95e>`* rlt
	);

.. _details-global:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Typedefs
--------

.. index:: pair: typedef; GstAnalyticsKeypointsMtd
.. _doxid-gstanalyticskeypointsmtd_8h_1afb01b2e17e7cfcdc9a61148cc0e1c49d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef typedefG_BEGIN_DECLS struct _GstAnalyticsMtd GstAnalyticsKeypointsMtd

GstAnalyticsKeypointsMtd: @id: Instance identifier. @meta: Instance of #GstAnalyticsRelationMeta where the analysis-metadata identified by @id is stored.

Handle containing data required to use gst_analytics_keypoints_mtd APIs. This type is generally expected to be allocated on the stack.

Since: 1.26

Global Functions
----------------

.. index:: pair: function; gst_gva_json_meta_get_info
.. _doxid-gva__json__meta_8h_1aa3e2cbd81b77b33be3a69a11c190cb57:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const GstMetaInfo* gst_gva_json_meta_get_info(void)

This function registers, if needed, and returns GstMetaInfo for :ref:`_GstGVAJSONMeta <doxid-struct___gst_g_v_a_j_s_o_n_meta>`.



.. rubric:: Returns:

const GstMetaInfo* for registered type

.. index:: pair: function; gst_gva_json_meta_api_get_type
.. _doxid-gva__json__meta_8h_1a4136c51ca9905bc6da7a3536ca957899:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GType gst_gva_json_meta_api_get_type(void)

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
.. _doxid-gva__tensor__meta_8h_1a09753594569dbadb68669cdddf5bdad1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	const GstMetaInfo* gst_gva_tensor_meta_get_info(void)

This function registers, if needed, and returns GstMetaInfo for :ref:`_GstGVATensorMeta <doxid-struct___gst_g_v_a_tensor_meta>`.



.. rubric:: Returns:

GstMetaInfo* for registered type

.. index:: pair: function; gst_gva_tensor_meta_api_get_type
.. _doxid-gva__tensor__meta_8h_1ac5b45e42b95ae7bb4bd51711551fd3c1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	GType gst_gva_tensor_meta_api_get_type(void)

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

