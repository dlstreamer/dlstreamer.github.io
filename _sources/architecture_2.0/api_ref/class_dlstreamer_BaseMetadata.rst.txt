.. index:: pair: class; dlstreamer::BaseMetadata
.. _doxid-classdlstreamer_1_1_base_metadata:

class dlstreamer::BaseMetadata
==============================

.. toctree::
	:hidden:




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <metadata.h>
	
	class BaseMetadata: public :ref:`dlstreamer::Metadata<doxid-classdlstreamer_1_1_metadata>` {
	public:
		// methods
	
		virtual void :target:`clear<doxid-classdlstreamer_1_1_base_metadata_1ad138d6a7ad5b0847711f5c378e43b170>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`begin<doxid-classdlstreamer_1_1_base_metadata_1af35be300becba4ab6d8bfd58f3179f90>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`end<doxid-classdlstreamer_1_1_base_metadata_1a67f927818423888d56b573e2b8818df0>`();
		virtual :ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` :target:`erase<doxid-classdlstreamer_1_1_base_metadata_1aed88e6bbbb4bb6739eec4a4e30297590>`(:ref:`iterator<doxid-classdlstreamer_1_1_metadata_1acc5d5f5b8001e3c473d8b2d33a6e9df6>` pos);
		virtual :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`add<doxid-classdlstreamer_1_1_base_metadata_1af1a50b222a92283a212e742ea4fe6ead>`(std::string_view name);
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
		virtual void :ref:`clear<doxid-classdlstreamer_1_1_metadata_1a7fb81693b271b5408e6a89024085efb3>`() = 0;

