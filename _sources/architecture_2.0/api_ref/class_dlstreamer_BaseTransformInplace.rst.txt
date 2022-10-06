.. index:: pair: class; dlstreamer::BaseTransformInplace
.. _doxid-classdlstreamer_1_1_base_transform_inplace:

class dlstreamer::BaseTransformInplace
======================================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <transform.h>
	
	class BaseTransformInplace: public :ref:`dlstreamer::BaseElement<doxid-classdlstreamer_1_1_base_element>` {
	public:
		// construction
	
		:target:`BaseTransformInplace<doxid-classdlstreamer_1_1_base_transform_inplace_1a61ae8fa601b3072c646e936b77aef21c>`(const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context);

		// methods
	
		virtual void :ref:`set_info<doxid-classdlstreamer_1_1_base_transform_inplace_1af6fe74912cd0364931b078d97e0e20c0>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_base_transform_inplace_1a0a87a7da7a1b08ae078ff0650952ae54>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src);
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_base_transform_inplace_1a155dca9127f88242a2ccc4685d90d5f1>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src);
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		bool :ref:`init<doxid-classdlstreamer_1_1_base_element_1a71225d2750ff83e2f568846affa17b76>`();
		:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_base_element_1aed010476c86c9db2f4814416477c6432>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`);

.. _details-classdlstreamer_1_1_base_transform_inplace:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; set_info
.. _doxid-classdlstreamer_1_1_base_transform_inplace_1af6fe74912cd0364931b078d97e0e20c0:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info)

The function notifies element about frame information.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>` information

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_base_transform_inplace_1a0a87a7da7a1b08ae078ff0650952ae54:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src)

Process frame.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Frame <doxid-classdlstreamer_1_1_frame>`

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_base_transform_inplace_1a155dca9127f88242a2ccc4685d90d5f1:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src)

Process tensor.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- :ref:`Tensor <doxid-classdlstreamer_1_1_tensor>`

