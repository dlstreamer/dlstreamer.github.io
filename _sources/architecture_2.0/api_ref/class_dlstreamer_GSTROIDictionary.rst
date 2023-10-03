.. index:: pair: class; dlstreamer::GSTROIDictionary
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary:

class dlstreamer::GSTROIDictionary
==================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <dictionary.h>
	
	class GSTROIDictionary: public :ref:`dlstreamer::Dictionary<doxid-classdlstreamer_1_1_dictionary>` {
	public:
		// typedefs
	
		typedef :ref:`DetectionMetadata::key<doxid-structdlstreamer_1_1_detection_metadata_1_1key>` :target:`key<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1aa43846b15af6d34f12f2f709cbcd0ad1>`;

		// construction
	
		:target:`GSTROIDictionary<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a0457dbaaab9402d0aee160b9226f536a>`(
			GstVideoRegionOfInterestMeta* roi,
			int width,
			int height,
			GstStructure* structure
		);

		// methods
	
		virtual std::string :ref:`name<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1ab718385b9b2e8971154c130b03603fc4>`() const;
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a3b72c5b978a08209afa8d73d6eb62394>`() const;
		virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :ref:`try_get<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a4b211f580ed3310bed576d04f51b94db>`(std::string_view key) const;
		virtual void :ref:`set<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a13cdecde5bd15c44086dd45bda57b108>`(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value);
		virtual std::pair<const void*, size_t> :ref:`try_get_array<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a002a35fdc2f22a76b3de32b115001a87>`(std::string_view key) const;
		virtual void :ref:`set_array<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1afd4d504b64a7b8d297c20f2842720740>`(std::string_view key, const void* data, size_t nbytes);
		virtual void :ref:`set_name<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1ab3588dd3ed0d2d92ee378e67b23cfecd>`(std::string const& name);
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		virtual std::string :ref:`name<doxid-classdlstreamer_1_1_dictionary_1a0b3ae50e8e01b3e63aebc5ae55735931>`() const = 0;
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_dictionary_1a3bf8b56e3372c43db14063c1d0fa783c>`() const = 0;
		virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :ref:`try_get<doxid-classdlstreamer_1_1_dictionary_1a91ef8bc0807e8f27a4cd08eac5e073ae>`(std::string_view key) const = 0;
		virtual std::pair<const void*, size_t> :ref:`try_get_array<doxid-classdlstreamer_1_1_dictionary_1a8038122a2247af7d49c0538983fb4587>`(std::string_view key) const = 0;
		virtual void :ref:`set<doxid-classdlstreamer_1_1_dictionary_1a07d06ea3a8f9905f2db71171792608a3>`(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value) = 0;
		virtual void :ref:`set_array<doxid-classdlstreamer_1_1_dictionary_1ac2cea5376a4fa4033d1e606b619c3176>`(std::string_view key, const void* data, size_t nbytes) = 0;
		virtual void :ref:`set_name<doxid-classdlstreamer_1_1_dictionary_1a53e8ef5840d033ad145f2955f8cf181d>`(std::string const& name) = 0;
	
		template <typename T>
		T :ref:`get<doxid-classdlstreamer_1_1_dictionary_1a1d6204f7da82bed3fe5762f3f52513bb>`(std::string_view key) const;
	
		template <typename T>
		T :ref:`get<doxid-classdlstreamer_1_1_dictionary_1a96b9134b9349c562f9a25a6065a03676>`(std::string_view key, T default_value) const;
	
		template <class T>
		const std::vector<T> :ref:`get_array<doxid-classdlstreamer_1_1_dictionary_1a2552c3e81c18df3561e82de0b51ac353>`(std::string_view key) const;

.. _details-classdlstreamer_1_1_g_s_t_r_o_i_dictionary:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; name
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1ab718385b9b2e8971154c130b03603fc4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::string name() const

Returns dictionary name. Utility function find_metadata uses it to find metadata by specified name.

.. index:: pair: function; keys
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a3b72c5b978a08209afa8d73d6eb62394:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::vector<std::string> keys() const

Returns a vector of all the available keys in the dictionary.

.. index:: pair: function; try_get
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a4b211f580ed3310bed576d04f51b94db:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> try_get(std::string_view key) const

Returns dictionary element by key. If no handle with the specified key, returns empty std::optional.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the dictionary element to find

.. index:: pair: function; set
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a13cdecde5bd15c44086dd45bda57b108:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value)

Adds element into the dictionary. If the dictionary already contains an element with specified key, the existing value will be overwritten.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the element to add

	*
		- value

		- the value of the element to add

.. index:: pair: function; try_get_array
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1a002a35fdc2f22a76b3de32b115001a87:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::pair<const void*, size_t> try_get_array(std::string_view key) const

Returns memory buffer stored in dictionary. The first element of returned std::pair is pointer to memory buffer, second element is buffer size in bytes. If no buffer with the specified key, returns {nullptr,0}.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the memory buffer to find

.. index:: pair: function; set_array
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1afd4d504b64a7b8d297c20f2842720740:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_array(std::string_view key, const void* data, size_t nbytes)

Allocates memory buffer and copies data from buffer specified in function parameters, and adds memory buffer to the dictionary. If the dictionary already contains an buffer with specified key, the existing buffer will be overwritten.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the memory buffer to add

	*
		- data

		- pointer to the memory buffer to add

	*
		- nbytes

		- size (in bytes) of the memory buffer to add

.. index:: pair: function; set_name
.. _doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary_1ab3588dd3ed0d2d92ee378e67b23cfecd:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_name(std::string const& name)

Sets name of dictionary. The existing name will be overwritten.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- dictionary name

