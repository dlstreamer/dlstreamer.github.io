.. index:: pair: class; dlstreamer::Transform
.. _doxid-classdlstreamer_1_1_transform:

class dlstreamer::Transform
===========================

.. toctree::
	:hidden:

Overview
~~~~~~~~

Abstract interface for transform elements. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element has one input and one output. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element is responsible for allocating output frame/tensor. :ref:`More...<details-classdlstreamer_1_1_transform>`


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <transform.h>
	
	class Transform: public :ref:`dlstreamer::Element<doxid-classdlstreamer_1_1_element>` {
	public:
		// methods
	
		virtual void :ref:`set_input_info<doxid-classdlstreamer_1_1_transform_1a262c38dba81e47f7656201d65b60b88e>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0;
		virtual void :ref:`set_output_info<doxid-classdlstreamer_1_1_transform_1a563364b5ed2c63ca803036b00e047829>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0;
		virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :ref:`get_input_info<doxid-classdlstreamer_1_1_transform_1a73690126670de109f146badb3d4606ad>`() = 0;
		virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :ref:`get_output_info<doxid-classdlstreamer_1_1_transform_1ab59ffcf5fba4a26947ae9a5db06bdd99>`() = 0;
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_transform_1a2cbdf551941027aec175360f121421f8>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` dst) = 0;
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_transform_1a123f7e78fb0e1213084a56901ec74074>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` dst) = 0;
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`process<doxid-classdlstreamer_1_1_transform_1a4c51b083ff551126bf6f9a5b250c8a7c>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src) = 0;
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`process<doxid-classdlstreamer_1_1_transform_1a31a3060981ade8ebc3cd2679b74e6465>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src) = 0;
	};

	// direct descendants

	template <class T>
	class :ref:`BaseElement<doxid-classdlstreamer_1_1_base_element>`;

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		virtual bool :ref:`init<doxid-classdlstreamer_1_1_element_1ae3c10fbab46b7f5cce7054fdec95b89f>`() = 0;
		virtual :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_element_1a64ab5ab3ed4c77ebce22d3874525783a>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type) = 0;

.. _details-classdlstreamer_1_1_transform:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~

Abstract interface for transform elements. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element has one input and one output. :ref:`Transform <doxid-classdlstreamer_1_1_transform>` element is responsible for allocating output frame/tensor.

Methods
-------

.. index:: pair: function; set_input_info
.. _doxid-classdlstreamer_1_1_transform_1a262c38dba81e47f7656201d65b60b88e:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_input_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0

The function notifies element about input information. Subsequent call to :ref:`get_output_info() <doxid-classdlstreamer_1_1_transform_1ab59ffcf5fba4a26947ae9a5db06bdd99>` should take into consideration input information passed via this function.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Input frames information

.. index:: pair: function; set_output_info
.. _doxid-classdlstreamer_1_1_transform_1a563364b5ed2c63ca803036b00e047829:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_output_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info) = 0

The function notifies element about output information. Subsequent call to :ref:`get_input_info() <doxid-classdlstreamer_1_1_transform_1a73690126670de109f146badb3d4606ad>` should take into consideration output information passed via this function.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; get_input_info
.. _doxid-classdlstreamer_1_1_transform_1a73690126670de109f146badb3d4606ad:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` get_input_info() = 0

Returns input information supported by element. It may depend on output information previously set by :ref:`set_output_info() <doxid-classdlstreamer_1_1_transform_1a563364b5ed2c63ca803036b00e047829>`.

.. index:: pair: function; get_output_info
.. _doxid-classdlstreamer_1_1_transform_1ab59ffcf5fba4a26947ae9a5db06bdd99:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` get_output_info() = 0

Returns output information supported by element. It may depend on input information previously set by :ref:`set_input_info() <doxid-classdlstreamer_1_1_transform_1a262c38dba81e47f7656201d65b60b88e>`.

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_1a2cbdf551941027aec175360f121421f8:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` dst) = 0

Run processing on input and output tensors.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- Input tensor

	*
		- dst

		- Output tensor

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_1a123f7e78fb0e1213084a56901ec74074:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` dst) = 0

Run processing on input and output frames.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- Input frame

	*
		- dst

		- Output frame

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_1a4c51b083ff551126bf6f9a5b250c8a7c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src) = 0

Process input tensor and return output tensor.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- Input frame

	*
		- dst

		- Output frame

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_transform_1a31a3060981ade8ebc3cd2679b74e6465:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src) = 0

Process input frame and return output frame.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- src

		- Input frame

	*
		- dst

		- Output frame

