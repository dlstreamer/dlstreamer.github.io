.. index:: pair: class; dlstreamer::GSTMetadata
.. _doxid-classdlstreamer_1_1_g_s_t_metadata:

class dlstreamer::GSTMetadata
=============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <metadata.h>
	
	class GSTMetadata: public :ref:`dlstreamer::Metadata<doxid-classdlstreamer_1_1_metadata>` {
	public:
		// construction
	
		:target:`GSTMetadata<doxid-classdlstreamer_1_1_g_s_t_metadata_1a1c550ff4d37346fc41569e04f7c1e517>`(GstBuffer* buf, const GstVideoInfo* video_info = nullptr);
		:target:`GSTMetadata<doxid-classdlstreamer_1_1_g_s_t_metadata_1a77f98732cf48919341d189d43ec3844f>`(GstBufferList* buffer_list);

		// methods
	
		:ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`find_metadata<doxid-classdlstreamer_1_1_g_s_t_metadata_1ac2dcf499b9fb8b13709016b28d51ce90>`(std::string_view meta_name);
		virtual void :target:`clear<doxid-classdlstreamer_1_1_g_s_t_metadata_1a3ca48910277c8ac8ea24a9de1e9d4179>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`begin<doxid-classdlstreamer_1_1_g_s_t_metadata_1a1ff9fa69065ed5aeb081e32319bcb414>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`end<doxid-classdlstreamer_1_1_g_s_t_metadata_1a8411cf5dfdb1c42ae3ff9450a638a6b1>`();
		virtual :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`add<doxid-classdlstreamer_1_1_g_s_t_metadata_1ac24c83f53e328a966d2a8c0b6d0d22a4>`(std::string_view name);
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`erase<doxid-classdlstreamer_1_1_g_s_t_metadata_1a7619a2da8107eaf335c0397d0da9a3fe>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` pos);
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

