.. index:: pair: class; gstgva::tensor::Tensor::PRECISION
.. _doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n:

class gstgva::tensor::Tensor::PRECISION
=======================================

.. toctree::
	:hidden:

This enum describes model layer precision.


.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	class PRECISION: public Enum {
	public:
		// fields
	
		static int :target:`UNSPECIFIED<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a43f115016f499e238818d6d84c8c76b1>` =  255;
		static int :target:`FP32<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1ad80dc731abfff7f70f4e97a5ae068344>` =  10;
		static int :target:`FP16<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1acbbdde00b21ce65a37ed0685ed6570af>` =  11;
		static int :target:`BF16<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1aa9792d8f93bd3ef40b6a50fed924127f>` =  12;
		static int :target:`FP64<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a2c84bd6dbbb2debec55fb055a83f98fb>` =  13;
		static int :target:`Q78<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a6f86bd1bb921909ac6a42ebef1283b74>` =  20;
		static int :target:`I16<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a0bfe00fc72bd7a59e8cee76ca1938583>` =  30;
		static int :target:`U4<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a43ba948eb6a28e384128e284bb99189e>` =  39;
		static int :target:`U8<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1ad0da3f4443090e6cd314f4d7807d0b61>` =  40;
		static int :target:`I4<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a8fcbea17c9984822b747588ab99f4ce2>` =  49;
		static int :target:`I8<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1aa94614bab0b6519450ccef49479542cf>` =  50;
		static int :target:`U16<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a325f73efb05accdb9b990c844fee7342>` =  60;
		static int :target:`I32<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a8697618069c0cfe7638e72f226b28dd7>` =  70;
		static int :target:`U32<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a18e7f516fc1b85990b13a5687a73ea13>` =  74;
		static int :target:`I64<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1ad57913c2bea425985d6a916afbaa44db>` =  72;
		static int :target:`U64<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1a65c44d1bd487663db81132519d04ddfc>` =  73;
		static int :target:`BIN<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1abe44010b72cc3038fcc23dbb99bdafc9>` =  71;
		static int :target:`BOOL<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1aefddee82c60da8088c4a9d0d589327fd>` =  41;
		static int :target:`CUSTOM<doxid-classgstgva_1_1tensor_1_1_tensor_1_1_p_r_e_c_i_s_i_o_n_1ab82140af7b8060b9486e21ad4ed2cc17>` =  80;
	};
