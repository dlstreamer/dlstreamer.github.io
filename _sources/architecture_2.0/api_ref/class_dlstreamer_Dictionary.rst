.. index:: pair: class; dlstreamer::Dictionary
.. _doxid-classdlstreamer_1_1_dictionary:

class dlstreamer::Dictionary
============================

.. toctree::
	:hidden:

Overview
~~~~~~~~

:ref:`Dictionary <doxid-classdlstreamer_1_1_dictionary>` is general-purpose key-value container. :ref:`More...<details-classdlstreamer_1_1_dictionary>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <dictionary.h>
	
	class Dictionary {
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
		T :target:`get<doxid-classdlstreamer_1_1_dictionary_1a1d6204f7da82bed3fe5762f3f52513bb>`(std::string_view key) const;
	
		template <typename T>
		T :target:`get<doxid-classdlstreamer_1_1_dictionary_1a96b9134b9349c562f9a25a6065a03676>`(std::string_view key, T default_value) const;
	
		template <class T>
		const std::vector<T> :target:`get_array<doxid-classdlstreamer_1_1_dictionary_1a2552c3e81c18df3561e82de0b51ac353>`(std::string_view key) const;
	};

	// direct descendants

	class :ref:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary>`;
	class :ref:`DictionaryProxy<doxid-classdlstreamer_1_1_dictionary_proxy>`;
	class :ref:`GSTDictionary<doxid-classdlstreamer_1_1_g_s_t_dictionary>`;
	class :ref:`GSTROIDictionary<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary>`;
.. _details-classdlstreamer_1_1_dictionary:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

:ref:`Dictionary <doxid-classdlstreamer_1_1_dictionary>` is general-purpose key-value container.

Methods
-------

.. index:: pair: function; name
.. _doxid-classdlstreamer_1_1_dictionary_1a0b3ae50e8e01b3e63aebc5ae55735931:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::string name() const = 0

Returns dictionary name. Utility function find_metadata uses it to find metadata by specified name.

.. index:: pair: function; keys
.. _doxid-classdlstreamer_1_1_dictionary_1a3bf8b56e3372c43db14063c1d0fa783c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::vector<std::string> keys() const = 0

Returns a vector of all the available keys in the dictionary.

.. index:: pair: function; try_get
.. _doxid-classdlstreamer_1_1_dictionary_1a91ef8bc0807e8f27a4cd08eac5e073ae:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> try_get(std::string_view key) const = 0

Returns dictionary element by key. If no handle with the specified key, returns empty std::optional.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the dictionary element to find

.. index:: pair: function; try_get_array
.. _doxid-classdlstreamer_1_1_dictionary_1a8038122a2247af7d49c0538983fb4587:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::pair<const void*, size_t> try_get_array(std::string_view key) const = 0

Returns memory buffer stored in dictionary. The first element of returned std::pair is pointer to memory buffer, second element is buffer size in bytes. If no buffer with the specified key, returns {nullptr,0}.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the memory buffer to find

.. index:: pair: function; set
.. _doxid-classdlstreamer_1_1_dictionary_1a07d06ea3a8f9905f2db71171792608a3:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value) = 0

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

.. index:: pair: function; set_array
.. _doxid-classdlstreamer_1_1_dictionary_1ac2cea5376a4fa4033d1e606b619c3176:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_array(std::string_view key, const void* data, size_t nbytes) = 0

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
.. _doxid-classdlstreamer_1_1_dictionary_1a53e8ef5840d033ad145f2955f8cf181d:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_name(std::string const& name) = 0

Sets name of dictionary. The existing name will be overwritten.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- name

		- dictionary name

