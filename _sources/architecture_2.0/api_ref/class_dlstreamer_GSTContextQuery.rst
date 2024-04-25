.. index:: pair: class; dlstreamer::GSTContextQuery
.. _doxid-classdlstreamer_1_1_g_s_t_context_query:

class dlstreamer::GSTContextQuery
=================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <context.h>
	
	class GSTContextQuery: public :ref:`dlstreamer::BaseContext<doxid-classdlstreamer_1_1_base_context>` {
	public:
		// construction
	
		:target:`GSTContextQuery<doxid-classdlstreamer_1_1_g_s_t_context_query_1a672c4894fc5565d874d84128e1c8e4b1>`(
			GstPad* pad,
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type,
			const char* context_name = nullptr
		);
	
		:target:`GSTContextQuery<doxid-classdlstreamer_1_1_g_s_t_context_query_1a5a008e2ef3fe38bff9eab2abb09a7e11>`(
			GstElement* element,
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type,
			const char* context_name = nullptr
		);
	
		:target:`GSTContextQuery<doxid-classdlstreamer_1_1_g_s_t_context_query_1ac413475e053fdb26a56802b57789f1ce>`(
			GstBaseTransform* element,
			:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type,
			const char* context_name = nullptr
		);

		// methods
	
		virtual :ref:`handle_t<doxid-classdlstreamer_1_1_context_1aca2855e33d7c60441af838d51fea6bbb>` :ref:`handle<doxid-classdlstreamer_1_1_g_s_t_context_query_1a17f49f34b48b481636df1ec0284779c3>`(std::string_view key) const;
	};

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

.. _details-classdlstreamer_1_1_g_s_t_context_query:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; handle
.. _doxid-classdlstreamer_1_1_g_s_t_context_query_1a17f49f34b48b481636df1ec0284779c3:

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

