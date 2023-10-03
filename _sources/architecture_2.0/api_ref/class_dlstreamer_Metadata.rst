.. index:: pair: class; dlstreamer::Metadata
.. _doxid-classdlstreamer_1_1_metadata:

class dlstreamer::Metadata
==========================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <metadata.h>
	
	class Metadata {
	public:
		// typedefs
	
		typedef std::vector<:ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>`>:::ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>`;

		// methods
	
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`begin<doxid-classdlstreamer_1_1_metadata_1a1480205564ff29ab7aa6f8317b71eae7>`() = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`end<doxid-classdlstreamer_1_1_metadata_1ae7525deebe5329c5862be0c5d64144c9>`() = 0;
		:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`begin<doxid-classdlstreamer_1_1_metadata_1a0d5fb64ad79e50c454890727013c8582>`() const;
		:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`end<doxid-classdlstreamer_1_1_metadata_1a57f3df030d2f34c874ebc23780c7ee36>`() const;
		virtual :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`add<doxid-classdlstreamer_1_1_metadata_1a4bb542ba1c659b24e50e4034755ae520>`(std::string_view name) = 0;
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`erase<doxid-classdlstreamer_1_1_metadata_1a81be521d875d613bfecaa0c9fc752c30>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` pos) = 0;
		virtual void :target:`clear<doxid-classdlstreamer_1_1_metadata_1a7fb81693b271b5408e6a89024085efb3>`() = 0;
	};

	// direct descendants

	class :ref:`BaseMetadata<doxid-classdlstreamer_1_1_base_metadata>`;
	class :ref:`GSTMetadata<doxid-classdlstreamer_1_1_g_s_t_metadata>`;
	class :ref:`GSTROIMetadata<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata>`;
