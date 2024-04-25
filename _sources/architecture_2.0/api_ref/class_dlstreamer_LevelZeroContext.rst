.. index:: pair: class; dlstreamer::LevelZeroContext
.. _doxid-classdlstreamer_1_1_level_zero_context:

class dlstreamer::LevelZeroContext
==================================

.. toctree::
	:hidden:

	struct_dlstreamer_LevelZeroContext_key.rst

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <context.h>
	
	class LevelZeroContext: public :ref:`dlstreamer::BaseContext<doxid-classdlstreamer_1_1_base_context>` {
	public:
		// structs
	
		struct :ref:`key<doxid-structdlstreamer_1_1_level_zero_context_1_1key>`;

		// construction
	
		:target:`LevelZeroContext<doxid-classdlstreamer_1_1_level_zero_context_1aa6a8d22eac4b8e8c40ebe92b4751b61e>`(
			ze_context_handle_t ze_context,
			ze_device_handle_t ze_device = nullptr
		);

		// methods
	
		ze_context_handle_t :target:`ze_context<doxid-classdlstreamer_1_1_level_zero_context_1ad3941f1d018090c6659cc82528871a18>`() const;
		ze_device_handle_t :target:`ze_device<doxid-classdlstreamer_1_1_level_zero_context_1ad0711fe276f3e76f150916154f487d92>`() const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_level_zero_context_1a75e338b530bb20c2bd20cfe26e766068>`(std::string_view key) const;
		virtual std::vector<std::string> :target:`keys<doxid-classdlstreamer_1_1_level_zero_context_1ab2a21fb3794886f76bbebb4c6ab8381e>`() const;
	
		virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`get_mapper<doxid-classdlstreamer_1_1_level_zero_context_1a114dc9530eebb1b57f378524a7800b2a>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		);
	};

	// direct descendants

	class :ref:`SYCLContext<doxid-classdlstreamer_1_1_s_y_c_l_context>`;

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// typedefs
	
		typedef void* :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>`;

		// structs
	
		struct :ref:`key<doxid-structdlstreamer_1_1_base_context_1_1key>`;

		// methods
	
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_context_1a44e6293399409827a27dc0c4c9086513>`() const = 0;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_context_1a4113a1b145145d2fea7c7af63a32b1ca>`(std::string_view key = {}) const = 0;
	
		virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`get_mapper<doxid-classdlstreamer_1_1_context_1a0985e3f26b899ef792886121da05592f>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		) = 0;
	
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`derive_context<doxid-classdlstreamer_1_1_context_1a705c49c9b7b1d2c5876f56b41b5915b6>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`parent<doxid-classdlstreamer_1_1_context_1accdd429d6425a607e3f4b8b17a98f5b1>`() = 0;
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_context_1a750d202dc0825e15508ebe03e28787e4>`() const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_base_context_1ade881599bb46ed4c72ab40106e04b218>`(std::string_view key) const;
		virtual std::vector<std::string> :ref:`keys<doxid-classdlstreamer_1_1_base_context_1ac1e2bf66ea1abdef6e14d8e8e9f26a51>`() const;
	
		virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`get_mapper<doxid-classdlstreamer_1_1_base_context_1a6864c141c7c298ae4e38156bfc168079>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		);
	
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`derive_context<doxid-classdlstreamer_1_1_base_context_1ac3ccb56746e2e464a5f7f6ba0dfa6022>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`parent<doxid-classdlstreamer_1_1_base_context_1a72681e6bf2aa6b4a1a80b683d725d916>`();
		void :ref:`set_parent<doxid-classdlstreamer_1_1_base_context_1a6080cfdb81b6a5a045b30b2353ba379d>`(:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` parent);
		void :ref:`set_memory_type<doxid-classdlstreamer_1_1_base_context_1aabfcb41ca0c0f874d0c559aac804285e>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);
		void :ref:`attach_mapper<doxid-classdlstreamer_1_1_base_context_1abc59c2f69eedbbaf9c65855bd920b8c7>`(:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` mapper);
		void :ref:`remove_mapper<doxid-classdlstreamer_1_1_base_context_1a8b16425adbb8ce4c58a55845b53ae421>`(:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` mapper);

.. _details-classdlstreamer_1_1_level_zero_context:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_level_zero_context_1a75e338b530bb20c2bd20cfe26e766068:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` handle(std::string_view key) const

Returns a handle by key. If empty key, returns default handle. If no handle with the specified key, returns 0.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- key

		- the key of the handle to find

.. index:: pair: function; get_mapper
.. _doxid-classdlstreamer_1_1_level_zero_context_1a114dc9530eebb1b57f378524a7800b2a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` get_mapper(
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
	)

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

