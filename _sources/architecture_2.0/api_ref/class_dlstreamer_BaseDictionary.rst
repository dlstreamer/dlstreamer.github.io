.. index:: pair: class; dlstreamer::BaseDictionary
.. _doxid-classdlstreamer_1_1_base_dictionary:

class dlstreamer::BaseDictionary
================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <dictionary.h>
	
	class BaseDictionary: public :ref:`dlstreamer::Dictionary<doxid-classdlstreamer_1_1_dictionary>` {
	public:
		// construction
	
		:target:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary_1ab78b42f75259140a958dc208146ae681>`();
		:target:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary_1a2b45c68db975bc3b7651fcf42ba1d765>`(std::string_view name);
		:target:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary_1a7bed5a8b76a88d7cbc36f9fb1074d59c>`(const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& map);
		:target:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary_1a232cdad548dbc83d855c4c1ef8c59303>`(const std::string& name, const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& map);

		// methods
	
		virtual std::string :ref:`name<doxid-classdlstreamer_1_1_base_dictionary_1ad0a6d1bf50ce0ec64375ac2c4b2833ff>`() const;
		virtual std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :ref:`try_get<doxid-classdlstreamer_1_1_base_dictionary_1aed85979e7f763345e41b9fda90b72b00>`(std::string_view key) const;
		virtual std::pair<const void*, size_t> :ref:`try_get_array<doxid-classdlstreamer_1_1_base_dictionary_1ad642ffcbac470fde8282ef3a2c591b3d>`(std::string_view key) const;
		virtual void :ref:`set<doxid-classdlstreamer_1_1_base_dictionary_1a74275609cd028e015713dc488deb375c>`(std::string_view key, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value);
		virtual void :ref:`set_array<doxid-classdlstreamer_1_1_base_dictionary_1a2ef54d2556db7420470ccd09bb2ee668>`(std::string_view key, const void* data, size_t nbytes);
		virtual void :ref:`set_name<doxid-classdlstreamer_1_1_base_dictionary_1a2fdf3b21dce1562f16efc6821006cce2>`(std::string const& name);
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_base_dictionary_1a7ead8d11cd747fbb22c852534aaea03a>`() const;
		bool :target:`operator <<doxid-classdlstreamer_1_1_base_dictionary_1ac430fd0de3552c65ea47c55d4ad4f8b7>` (const BaseDictionary& r) const;
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

.. _details-classdlstreamer_1_1_base_dictionary:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; name
.. _doxid-classdlstreamer_1_1_base_dictionary_1ad0a6d1bf50ce0ec64375ac2c4b2833ff:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::string name() const

Returns dictionary name. Utility function find_metadata uses it to find metadata by specified name.

.. index:: pair: function; try_get
.. _doxid-classdlstreamer_1_1_base_dictionary_1aed85979e7f763345e41b9fda90b72b00:

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

.. index:: pair: function; try_get_array
.. _doxid-classdlstreamer_1_1_base_dictionary_1ad642ffcbac470fde8282ef3a2c591b3d:

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

.. index:: pair: function; set
.. _doxid-classdlstreamer_1_1_base_dictionary_1a74275609cd028e015713dc488deb375c:

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

.. index:: pair: function; set_array
.. _doxid-classdlstreamer_1_1_base_dictionary_1a2ef54d2556db7420470ccd09bb2ee668:

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
.. _doxid-classdlstreamer_1_1_base_dictionary_1a2fdf3b21dce1562f16efc6821006cce2:

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

.. index:: pair: function; keys
.. _doxid-classdlstreamer_1_1_base_dictionary_1a7ead8d11cd747fbb22c852534aaea03a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual std::vector<std::string> keys() const

Returns a vector of all the available keys in the dictionary.

