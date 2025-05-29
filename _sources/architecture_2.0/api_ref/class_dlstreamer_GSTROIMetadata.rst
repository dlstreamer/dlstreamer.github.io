.. index:: pair: class; dlstreamer::GSTROIMetadata
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata:

class dlstreamer::GSTROIMetadata
================================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <metadata.h>
	
	class GSTROIMetadata: public :ref:`dlstreamer::Metadata<doxid-classdlstreamer_1_1_metadata>` {
	public:
		// construction
	
		:target:`GSTROIMetadata<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1a50003c6f3269915bf1897b8fb8c8ea71>`(
			GstVideoRegionOfInterestMeta* roi,
			const GstVideoInfo* video_info
		);

		// methods
	
		virtual void :target:`clear<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1ab7c97356fa6177a5a4c1c7115fc541ba>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`begin<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1a5df7cf8a0d9732a15a3e6298a273c70b>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`end<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1acdfa5bbe6bcbcda254473c6c6c784947>`();
		virtual :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`add<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1a71bf0595388057170915bf9a823c3755>`(std::string_view name);
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`erase<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata_1accbe959cf5e30f1c102931fff78f75fa>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` pos);
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// typedefs
	
		typedef std::vector<:ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>`>:::ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>`;

		// methods
	
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`begin<doxid-classdlstreamer_1_1_metadata_1a1480205564ff29ab7aa6f8317b71eae7>`() = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`end<doxid-classdlstreamer_1_1_metadata_1ae7525deebe5329c5862be0c5d64144c9>`() = 0;
		:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`begin<doxid-classdlstreamer_1_1_metadata_1a0d5fb64ad79e50c454890727013c8582>`() const;
		:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`end<doxid-classdlstreamer_1_1_metadata_1a57f3df030d2f34c874ebc23780c7ee36>`() const;
		virtual :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :ref:`add<doxid-classdlstreamer_1_1_metadata_1a4bb542ba1c659b24e50e4034755ae520>`(std::string_view name) = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`erase<doxid-classdlstreamer_1_1_metadata_1a81be521d875d613bfecaa0c9fc752c30>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` pos) = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :ref:`erase<doxid-classdlstreamer_1_1_metadata_1a11add24125e5b60dce46e0413577b6bc>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` first, :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` last);
		virtual void :ref:`clear<doxid-classdlstreamer_1_1_metadata_1a7fb81693b271b5408e6a89024085efb3>`() = 0;

