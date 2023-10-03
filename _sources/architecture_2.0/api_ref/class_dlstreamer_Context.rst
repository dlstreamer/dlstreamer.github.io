.. index:: pair: class; dlstreamer::Context
.. _doxid-classdlstreamer_1_1_context:

class dlstreamer::Context
=========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

This class represents context created on one of memory types listed in enum MemoryType. :ref:`Context <doxid-classdlstreamer_1_1_context>` contains one or multiple handles associated with underlying framework or memory type, for example handle with type cl_context and key "cl_context" if OpenCL memory type. :ref:`Context <doxid-classdlstreamer_1_1_context>` is capable to create memory mapping object for mapping to or from system memory, and potentially other memory types if supported by underlying framework. :ref:`Context <doxid-classdlstreamer_1_1_context>` is capable to create another context on same device, if supported by underlying framework. :ref:`More...<details-classdlstreamer_1_1_context>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <context.h>
	
	class Context {
	public:
		// typedefs
	
		typedef void* :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>`;

		// methods
	
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_context_1a44e6293399409827a27dc0c4c9086513>`() const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_context_1a4113a1b145145d2fea7c7af63a32b1ca>`(std::string_view key = {}) const = 0;
	
		virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`get_mapper<doxid-classdlstreamer_1_1_context_1a0985e3f26b899ef792886121da05592f>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		) = 0;
	
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`derive_context<doxid-classdlstreamer_1_1_context_1a705c49c9b7b1d2c5876f56b41b5915b6>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`parent<doxid-classdlstreamer_1_1_context_1accdd429d6425a607e3f4b8b17a98f5b1>`() = 0;
	};

	// direct descendants

	class :ref:`BaseContext<doxid-classdlstreamer_1_1_base_context>`;
.. _details-classdlstreamer_1_1_context:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

This class represents context created on one of memory types listed in enum MemoryType. :ref:`Context <doxid-classdlstreamer_1_1_context>` contains one or multiple handles associated with underlying framework or memory type, for example handle with type cl_context and key "cl_context" if OpenCL memory type. :ref:`Context <doxid-classdlstreamer_1_1_context>` is capable to create memory mapping object for mapping to or from system memory, and potentially other memory types if supported by underlying framework. :ref:`Context <doxid-classdlstreamer_1_1_context>` is capable to create another context on same device, if supported by underlying framework.

Typedefs
--------

.. index:: pair: typedef; handle_t
.. _doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef void* handle_t

Type of handles stored in context.

Methods
-------

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_context_1a44e6293399409827a27dc0c4c9086513:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const = 0

Returns memory type of this context.

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_context_1a4113a1b145145d2fea7c7af63a32b1ca:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` handle(std::string_view key = {}) const = 0

Returns a handle by key. If empty key, returns default handle. If no handle with the specified key, returns 0.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; get_mapper
.. _doxid-classdlstreamer_1_1_context_1a0985e3f26b899ef792886121da05592f:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` get_mapper(
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
	) = 0

Returns an object for memory mapping between two contexts. Function typically expects one of contexts to be this context. If one of contexts has memory type CPU or context reference is nullptr, function returns object for mapping to or from system memory. If creating memory mapping object failed, exception is thrown.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- input_context

		- :ref:`Context <doxid-classdlstreamer_1_1_context>` of input memory

	*
		- output_context

		- :ref:`Context <doxid-classdlstreamer_1_1_context>` of output memory

.. index:: pair: function; derive_context
.. _doxid-classdlstreamer_1_1_context_1a705c49c9b7b1d2c5876f56b41b5915b6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` derive_context(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0

Create another context of specified memory type. New context belongs to same device (if multiple GPUs) as original context, and :ref:`parent() <doxid-classdlstreamer_1_1_context_1accdd429d6425a607e3f4b8b17a98f5b1>` returns reference to original context. If creating new context failed, function returns nullptr.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- memory_type

		- Memory type of new context

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_context_1accdd429d6425a607e3f4b8b17a98f5b1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` parent() = 0

Returns parent context if this context was created from another context via :ref:`derive_context() <doxid-classdlstreamer_1_1_context_1a705c49c9b7b1d2c5876f56b41b5915b6>`, nullptr otherwise.

