.. index:: pair: class; dlstreamer::BaseTransform
.. _doxid-classdlstreamer_1_1_base_transform:

class dlstreamer::BaseTransform
===============================

.. toctree::
	:hidden:

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	#include <transform.h>
	
	class BaseTransform: public :ref:`dlstreamer::BaseElement<doxid-classdlstreamer_1_1_base_element>` {
	public:
		// construction
	
		:target:`BaseTransform<doxid-classdlstreamer_1_1_base_transform_1a6ce414cc2e5eba0e814d94dbd9b6ccb2>`(const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context);

		// methods
	
		virtual void :ref:`set_input_info<doxid-classdlstreamer_1_1_base_transform_1abc63a39ec34ae6b62681553139ded17c>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
		virtual void :ref:`set_output_info<doxid-classdlstreamer_1_1_base_transform_1a549f9e039dfcc470db897c37fa5099a6>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
		virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :ref:`get_input_info<doxid-classdlstreamer_1_1_base_transform_1a7f328d541780d9de2ec40754d6292f8b>`();
		virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` :ref:`get_output_info<doxid-classdlstreamer_1_1_base_transform_1ad2b102bf3b4c3d21d452d7c686b8d33a>`();
		virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` :ref:`process<doxid-classdlstreamer_1_1_base_transform_1a0ee678f2b148304b46251edba3b58fa5>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src);
		virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :ref:`process<doxid-classdlstreamer_1_1_base_transform_1ac7630cb002dbd7b08927ccb90508a9f6>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src);
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_base_transform_1a3c75bed1f38bc56e9dc6437617b1f033>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` dst);
		virtual bool :ref:`process<doxid-classdlstreamer_1_1_base_transform_1a2b5649329412939c055895e8f1535b06>`(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` dst);
		size_t :target:`pool_size<doxid-classdlstreamer_1_1_base_transform_1aa2c9cb3c7853b5050e728c7bc3e2b2b7>`();
	};

Inherited Members
-----------------

.. ref-code-block:: cpp
	:class: doxyrest-overview-inherited-code-block

	public:
		// methods
	
		bool :ref:`init<doxid-classdlstreamer_1_1_base_element_1a71225d2750ff83e2f568846affa17b76>`();
		:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>` :ref:`get_context<doxid-classdlstreamer_1_1_base_element_1aed010476c86c9db2f4814416477c6432>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`);

.. _details-classdlstreamer_1_1_base_transform:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Methods
-------

.. index:: pair: function; set_input_info
.. _doxid-classdlstreamer_1_1_base_transform_1abc63a39ec34ae6b62681553139ded17c:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_input_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info)

The function notifies element about input information. Subsequent call to :ref:`get_output_info() <doxid-classdlstreamer_1_1_base_transform_1ad2b102bf3b4c3d21d452d7c686b8d33a>` should take into consideration input information passed via this function.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Input frames information

.. index:: pair: function; set_output_info
.. _doxid-classdlstreamer_1_1_base_transform_1a549f9e039dfcc470db897c37fa5099a6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual void set_output_info(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info)

The function notifies element about output information. Subsequent call to :ref:`get_input_info() <doxid-classdlstreamer_1_1_base_transform_1a7f328d541780d9de2ec40754d6292f8b>` should take into consideration output information passed via this function.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- info

		- Output frames information

.. index:: pair: function; get_input_info
.. _doxid-classdlstreamer_1_1_base_transform_1a7f328d541780d9de2ec40754d6292f8b:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` get_input_info()

Returns input information supported by element. It may depend on output information previously set by :ref:`set_output_info() <doxid-classdlstreamer_1_1_base_transform_1a549f9e039dfcc470db897c37fa5099a6>`.

.. index:: pair: function; get_output_info
.. _doxid-classdlstreamer_1_1_base_transform_1ad2b102bf3b4c3d21d452d7c686b8d33a:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>` get_output_info()

Returns output information supported by element. It may depend on input information previously set by :ref:`set_input_info() <doxid-classdlstreamer_1_1_base_transform_1abc63a39ec34ae6b62681553139ded17c>`.

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_base_transform_1a0ee678f2b148304b46251edba3b58fa5:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src)

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

.. index:: pair: function; process
.. _doxid-classdlstreamer_1_1_base_transform_1ac7630cb002dbd7b08927ccb90508a9f6:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src)

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
.. _doxid-classdlstreamer_1_1_base_transform_1a3c75bed1f38bc56e9dc6437617b1f033:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` src, :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` dst)

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
.. _doxid-classdlstreamer_1_1_base_transform_1a2b5649329412939c055895e8f1535b06:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	virtual bool process(:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` src, :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` dst)

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

