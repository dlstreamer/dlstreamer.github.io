.. index:: pair: class; dlstreamer::BaseContext
.. _doxid-classdlstreamer_1_1_base_context:

class dlstreamer::BaseContext
=============================

.. toctree::
	:hidden:

	struct_dlstreamer_BaseContext_key.rst

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <context.h>
	
	class BaseContext: public :ref:`dlstreamer::Context<doxid-classdlstreamer_1_1_context>` {
	public:
		// structs
	
		struct :ref:`key<doxid-structdlstreamer_1_1_base_context_1_1key>`;

		// construction
	
		:target:`BaseContext<doxid-classdlstreamer_1_1_base_context_1a860a5c69345c947ef47301749ee85967>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);

		// methods
	
		virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :ref:`memory_type<doxid-classdlstreamer_1_1_base_context_1a750d202dc0825e15508ebe03e28787e4>`() const;
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_base_context_1ade881599bb46ed4c72ab40106e04b218>`(std::string_view key) const;
		virtual std::vector<std::string> :target:`keys<doxid-classdlstreamer_1_1_base_context_1ac1e2bf66ea1abdef6e14d8e8e9f26a51>`() const;
	
		virtual :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`get_mapper<doxid-classdlstreamer_1_1_base_context_1a6864c141c7c298ae4e38156bfc168079>`(
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& input_context,
			const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& output_context
		);
	
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`derive_context<doxid-classdlstreamer_1_1_base_context_1ac3ccb56746e2e464a5f7f6ba0dfa6022>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`parent<doxid-classdlstreamer_1_1_base_context_1a72681e6bf2aa6b4a1a80b683d725d916>`();
		void :target:`set_parent<doxid-classdlstreamer_1_1_base_context_1a6080cfdb81b6a5a045b30b2353ba379d>`(:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` parent);
		void :target:`set_memory_type<doxid-classdlstreamer_1_1_base_context_1aabfcb41ca0c0f874d0c559aac804285e>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);
		void :target:`attach_mapper<doxid-classdlstreamer_1_1_base_context_1abc59c2f69eedbbaf9c65855bd920b8c7>`(:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` mapper);
		void :target:`remove_mapper<doxid-classdlstreamer_1_1_base_context_1a8b16425adbb8ce4c58a55845b53ae421>`(:ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` mapper);
	};

	// direct descendants

	class :ref:`CPUContext<doxid-classdlstreamer_1_1_c_p_u_context>`;
	class :ref:`DMAContext<doxid-classdlstreamer_1_1_d_m_a_context>`;
	class :ref:`FFmpegContext<doxid-classdlstreamer_1_1_f_fmpeg_context>`;
	class :ref:`GSTContext<doxid-classdlstreamer_1_1_g_s_t_context>`;
	class :ref:`GSTContextQuery<doxid-classdlstreamer_1_1_g_s_t_context_query>`;
	class :ref:`LevelZeroContext<doxid-classdlstreamer_1_1_level_zero_context>`;
	class :ref:`OpenCLContext<doxid-classdlstreamer_1_1_open_c_l_context>`;
	class :ref:`OpenCVContext<doxid-classdlstreamer_1_1_open_c_v_context>`;
	class :ref:`OpenCVUMatContext<doxid-classdlstreamer_1_1_open_c_v_u_mat_context>`;
	class :ref:`OpenVINOContext<doxid-classdlstreamer_1_1_open_v_i_n_o_context>`;
	class :ref:`VAAPIContext<doxid-classdlstreamer_1_1_v_a_a_p_i_context>`;

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

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

.. _details-classdlstreamer_1_1_base_context:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; memory_type
.. _doxid-classdlstreamer_1_1_base_context_1a750d202dc0825e15508ebe03e28787e4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type() const

Returns memory type of this context.

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_base_context_1ade881599bb46ed4c72ab40106e04b218:

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
.. _doxid-classdlstreamer_1_1_base_context_1a6864c141c7c298ae4e38156bfc168079:

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

.. index:: pair: function; derive_context
.. _doxid-classdlstreamer_1_1_base_context_1ac3ccb56746e2e464a5f7f6ba0dfa6022:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` derive_context(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type)

Create another context of specified memory type. New context belongs to same device (if multiple GPUs) as original context, and :ref:`parent() <doxid-classdlstreamer_1_1_base_context_1a72681e6bf2aa6b4a1a80b683d725d916>` returns reference to original context. If creating new context failed, function returns nullptr.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- memory_type

		- Memory type of new context

.. index:: pair: function; parent
.. _doxid-classdlstreamer_1_1_base_context_1a72681e6bf2aa6b4a1a80b683d725d916:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` parent()

Returns parent context if this context was created from another context via :ref:`derive_context() <doxid-classdlstreamer_1_1_base_context_1ac3ccb56746e2e464a5f7f6ba0dfa6022>`, nullptr otherwise.

