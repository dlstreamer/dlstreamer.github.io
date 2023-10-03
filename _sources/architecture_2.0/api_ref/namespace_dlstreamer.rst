.. index:: pair: namespace; dlstreamer
.. _doxid-namespacedlstreamer:

namespace dlstreamer
====================

.. toctree::
	:hidden:

	namespace_dlstreamer_detail.rst
	namespace_dlstreamer_param.rst
	namespace_dlstreamer_tensor.rst
	enum_dlstreamer_AccessMode.rst
	enum_dlstreamer_DataType.rst
	enum_dlstreamer_ElementFlags.rst
	enum_dlstreamer_ImageFormat.rst
	enum_dlstreamer_MediaType.rst
	enum_dlstreamer_MemoryType.rst
	struct_dlstreamer_AudioFormat.rst
	struct_dlstreamer_AudioInfo.rst
	struct_dlstreamer_ElementDesc.rst
	struct_dlstreamer_FrameInfo.rst
	struct_dlstreamer_GstDLStreamerMemory.rst
	struct_dlstreamer_ImageInfo.rst
	struct_dlstreamer_ParamDesc.rst
	struct_dlstreamer_TensorInfo.rst
	class_dlstreamer_AffineTransformInfoMetadata.rst
	class_dlstreamer_BaseContext.rst
	class_dlstreamer_BaseDictionary.rst
	class_dlstreamer_BaseElement.rst
	class_dlstreamer_BaseFrame.rst
	class_dlstreamer_BaseMemoryMapper.rst
	class_dlstreamer_BaseMetadata.rst
	class_dlstreamer_BaseSink.rst
	class_dlstreamer_BaseSource.rst
	class_dlstreamer_BaseTensor.rst
	class_dlstreamer_BaseTransform.rst
	class_dlstreamer_BaseTransformInplace.rst
	class_dlstreamer_BlockingQueue.rst
	class_dlstreamer_CPUContext.rst
	class_dlstreamer_CPUFrameAlloc.rst
	class_dlstreamer_CPUTensor.rst
	class_dlstreamer_CPUTensorAlloc.rst
	class_dlstreamer_ClassificationMetadata.rst
	class_dlstreamer_Context.rst
	class_dlstreamer_DMAContext.rst
	class_dlstreamer_DMATensor.rst
	class_dlstreamer_DetectionMetadata.rst
	class_dlstreamer_Dictionary.rst
	class_dlstreamer_DictionaryProxy.rst
	class_dlstreamer_Element.rst
	class_dlstreamer_FFmpegContext.rst
	class_dlstreamer_FFmpegFrame.rst
	class_dlstreamer_Frame.rst
	class_dlstreamer_FramePtr.rst
	class_dlstreamer_GSTContext.rst
	class_dlstreamer_GSTContextQuery.rst
	class_dlstreamer_GSTDictionary.rst
	class_dlstreamer_GSTFrame.rst
	class_dlstreamer_GSTFrameBatch.rst
	class_dlstreamer_GSTMetadata.rst
	class_dlstreamer_GSTROIDictionary.rst
	class_dlstreamer_GSTROIMetadata.rst
	class_dlstreamer_GSTTensor.rst
	class_dlstreamer_ImageLayout.rst
	class_dlstreamer_InferenceResultMetadata.rst
	class_dlstreamer_LevelZeroContext.rst
	class_dlstreamer_MemoryMapper.rst
	class_dlstreamer_MemoryMapperAnyToGST.rst
	class_dlstreamer_MemoryMapperCPUToOpenCV.rst
	class_dlstreamer_MemoryMapperCPUToOpenVINO.rst
	class_dlstreamer_MemoryMapperCache.rst
	class_dlstreamer_MemoryMapperChain.rst
	class_dlstreamer_MemoryMapperDMAToOpenCL.rst
	class_dlstreamer_MemoryMapperDMAToUSM.rst
	class_dlstreamer_MemoryMapperDMAToVAAPI.rst
	class_dlstreamer_MemoryMapperFFMPEGToVAAPI.rst
	class_dlstreamer_MemoryMapperGSTToDMA.rst
	class_dlstreamer_MemoryMapperGSTToOpenCL.rst
	class_dlstreamer_MemoryMapperGSTToVAAPI.rst
	class_dlstreamer_MemoryMapperOpenCLToCPU.rst
	class_dlstreamer_MemoryMapperOpenCLToDMA.rst
	class_dlstreamer_MemoryMapperOpenCLToOpenCVUMat.rst
	class_dlstreamer_MemoryMapperOpenCLToOpenVINO.rst
	class_dlstreamer_MemoryMapperOpenVINOToCPU.rst
	class_dlstreamer_MemoryMapperSYCLUSMToCPU.rst
	class_dlstreamer_MemoryMapperUSMToDMA.rst
	class_dlstreamer_MemoryMapperVAAPIToDMA.rst
	class_dlstreamer_MemoryMapperVAAPIToOpenVINO.rst
	class_dlstreamer_Metadata.rst
	class_dlstreamer_ModelInfoMetadata.rst
	class_dlstreamer_ObjectIdMetadata.rst
	class_dlstreamer_OpenCLContext.rst
	class_dlstreamer_OpenCLTensor.rst
	class_dlstreamer_OpenCLTensorRefCounted.rst
	class_dlstreamer_OpenCVContext.rst
	class_dlstreamer_OpenCVTensor.rst
	class_dlstreamer_OpenCVUMatContext.rst
	class_dlstreamer_OpenCVUMatTensor.rst
	class_dlstreamer_OpenVINOContext.rst
	class_dlstreamer_OpenVINOFrame.rst
	class_dlstreamer_OpenVINOTensor.rst
	class_dlstreamer_OpenVINOTensorBatch.rst
	class_dlstreamer_Pool.rst
	class_dlstreamer_SYCLContext.rst
	class_dlstreamer_SYCLUSMTensor.rst
	class_dlstreamer_Sink.rst
	class_dlstreamer_Source.rst
	class_dlstreamer_SourceIdentifierMetadata.rst
	class_dlstreamer_Tensor.rst
	class_dlstreamer_TensorPtr.rst
	class_dlstreamer_TimestampMetadata.rst
	class_dlstreamer_Transform.rst
	class_dlstreamer_TransformInplace.rst
	class_dlstreamer_USMTensor.rst
	class_dlstreamer_VAAPIContext.rst
	class_dlstreamer_VAAPIFrame.rst
	class_dlstreamer_VAAPIFrameAlloc.rst
	class_dlstreamer_VAAPITensor.rst

Overview
~~~~~~~~




.. ref-code-block:: cpp
	:class: doxyrest-overview-code-block

	
	namespace dlstreamer {

	// namespaces

	namespace :ref:`dlstreamer::detail<doxid-namespacedlstreamer_1_1detail>`;
	namespace :ref:`dlstreamer::param<doxid-namespacedlstreamer_1_1param>`;
	namespace :ref:`dlstreamer::tensor<doxid-namespacedlstreamer_1_1tensor>`;
		namespace :ref:`dlstreamer::tensor::key<doxid-namespacedlstreamer_1_1tensor_1_1key>`;

	// typedefs

	typedef std::shared_ptr<:ref:`BaseFrame<doxid-classdlstreamer_1_1_base_frame>`> :target:`BaseFramePtr<doxid-namespacedlstreamer_1a245c22ae194eb3d18422b681cc105a61>`;
	typedef std::shared_ptr<:ref:`BaseSink<doxid-classdlstreamer_1_1_base_sink>`> :target:`BaseSinkPtr<doxid-namespacedlstreamer_1ac8ec2c82a6db4f21a1d5bfcef750e411>`;
	typedef std::shared_ptr<:ref:`BaseSource<doxid-classdlstreamer_1_1_base_source>`> :target:`BaseSourcePtr<doxid-namespacedlstreamer_1afaf3a20e543b9d82f7ded7f3f6682958>`;
	typedef std::shared_ptr<:ref:`BaseTransform<doxid-classdlstreamer_1_1_base_transform>`> :target:`BaseTransformPtr<doxid-namespacedlstreamer_1ab741de7c7111c893fc82c9ddfa6582cf>`;
	typedef std::shared_ptr<:ref:`Context<doxid-classdlstreamer_1_1_context>`> :target:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`;
	typedef std::shared_ptr<:ref:`MemoryMapper<doxid-classdlstreamer_1_1_memory_mapper>`> :target:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>`;
	typedef std::shared_ptr<:ref:`CPUContext<doxid-classdlstreamer_1_1_c_p_u_context>`> :target:`CPUContextPtr<doxid-namespacedlstreamer_1a200c2b09b523905681ad9a67febb7fff>`;
	typedef std::shared_ptr<:ref:`CPUTensor<doxid-classdlstreamer_1_1_c_p_u_tensor>`> :target:`CPUTensorPtr<doxid-namespacedlstreamer_1a4d0c966a6e8dffdab16c10cf40c7e315>`;
	typedef std::variant<int, double, size_t, std::string, std::vector<int>, std::vector<double>, std::vector<size_t>, std::vector<std::string>, intptr_t, bool, std::pair<int, int>> :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`;
	typedef std::map<std::string, :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`, std::less<void>> :target:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`;
	typedef std::shared_ptr<:ref:`Dictionary<doxid-classdlstreamer_1_1_dictionary>`> :target:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>`;
	typedef std::shared_ptr<const :ref:`Dictionary<doxid-classdlstreamer_1_1_dictionary>`> :target:`DictionaryCPtr<doxid-namespacedlstreamer_1a8407dcbf0aebfcb357acad3ac2d27bfc>`;
	typedef std::shared_ptr<:ref:`DMAContext<doxid-classdlstreamer_1_1_d_m_a_context>`> :target:`DMAContextPtr<doxid-namespacedlstreamer_1a6da150094fe9002df7d1405742b725ed>`;
	typedef std::shared_ptr<:ref:`DMATensor<doxid-classdlstreamer_1_1_d_m_a_tensor>`> :target:`DMATensorPtr<doxid-namespacedlstreamer_1a7c76a05a98266c7c18c4c2c71e63c3c2>`;
	typedef std::shared_ptr<:ref:`Element<doxid-classdlstreamer_1_1_element>`> :target:`ElementPtr<doxid-namespacedlstreamer_1ae66a7cb3f12db3c71b507f28cfa950f2>`;
	typedef std::vector<:ref:`ParamDesc<doxid-structdlstreamer_1_1_param_desc>`> :target:`ParamDescVector<doxid-namespacedlstreamer_1a1c0d94608894c5255d65851870d3a184>`;
	typedef std::shared_ptr<:ref:`FFmpegContext<doxid-classdlstreamer_1_1_f_fmpeg_context>`> :target:`FFmpegContextPtr<doxid-namespacedlstreamer_1a229ecdbe4c38c550e144d3aa8a507c33>`;
	typedef std::shared_ptr<:ref:`FFmpegFrame<doxid-classdlstreamer_1_1_f_fmpeg_frame>`> :target:`FFmpegFramePtr<doxid-namespacedlstreamer_1aa3da3375cf9341ad2c2bb470590279bf>`;
	typedef int64_t :target:`Format<doxid-namespacedlstreamer_1acfddbd36bfab06a818f4c2a32613eb96>`;
	typedef std::vector<:ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`> :target:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>`;
	typedef std::shared_ptr<:ref:`GSTFrame<doxid-classdlstreamer_1_1_g_s_t_frame>`> :target:`GstFramePtr<doxid-namespacedlstreamer_1aa8eec5041f919584a28a14dd775bd9be>`;
	typedef std::shared_ptr<:ref:`GSTTensor<doxid-classdlstreamer_1_1_g_s_t_tensor>`> :target:`GstTensorPtr<doxid-namespacedlstreamer_1af63c902c90cd015c11d127f972d32807>`;
	typedef std::shared_ptr<:ref:`USMTensor<doxid-classdlstreamer_1_1_u_s_m_tensor>`> :target:`USMTensorPtr<doxid-namespacedlstreamer_1a7480cf1dd4864f7f587e3929b9c11c21>`;
	typedef std::shared_ptr<:ref:`OpenCLContext<doxid-classdlstreamer_1_1_open_c_l_context>`> :target:`OpenCLContextPtr<doxid-namespacedlstreamer_1a7f761081c52f1b65cbedc172ace99982>`;

	typedef CL_API_ENTRY :ref:`cl_mem<doxid-opencl_2tensor_8h_1af2141916ad9655073b9810d7bc71494d>`(CL_API_CALL* :target:`clCreateBufferWithPropertiesINTEL_fn<doxid-namespacedlstreamer_1a0771493631cde755f1d301c5ef0d5bd3>`)(
		cl_context context,
		const cl_bitfield *properties,
		cl_mem_flags flags,
		size_t size,
		void *host_ptr,
		cl_int *errcode_ret
		);

	typedef std::shared_ptr<:ref:`OpenCLTensor<doxid-classdlstreamer_1_1_open_c_l_tensor>`> :target:`OpenCLTensorPtr<doxid-namespacedlstreamer_1aea8a79b8847a6f65bc904aaabe89f194>`;
	typedef std::shared_ptr<:ref:`OpenCVContext<doxid-classdlstreamer_1_1_open_c_v_context>`> :target:`OpenCVContextPtr<doxid-namespacedlstreamer_1a4ac3dd08f732cda0cf75aa908f643388>`;
	typedef std::shared_ptr<:ref:`OpenCVTensor<doxid-classdlstreamer_1_1_open_c_v_tensor>`> :target:`OpenCVTensorPtr<doxid-namespacedlstreamer_1a1f8b374078d438ed4f3337fafffc4921>`;
	typedef std::shared_ptr<:ref:`OpenCVUMatContext<doxid-classdlstreamer_1_1_open_c_v_u_mat_context>`> :target:`OpenCVUMatContextPtr<doxid-namespacedlstreamer_1acfd3ae66f815f2d837fd2a8c334cdef4>`;
	typedef std::shared_ptr<:ref:`OpenCVUMatTensor<doxid-classdlstreamer_1_1_open_c_v_u_mat_tensor>`> :target:`OpenCVUMatTensorPtr<doxid-namespacedlstreamer_1a3bf699dd14e7bf49d9178936e2a72062>`;
	typedef std::shared_ptr<:ref:`OpenVINOContext<doxid-classdlstreamer_1_1_open_v_i_n_o_context>`> :target:`OpenVINOContextPtr<doxid-namespacedlstreamer_1ac0e51f0c3ed7558e4494b81862282db6>`;
	typedef std::shared_ptr<:ref:`OpenVINOFrame<doxid-classdlstreamer_1_1_open_v_i_n_o_frame>`> :target:`OpenVINOFramePtr<doxid-namespacedlstreamer_1ae8a3b8f0778f7f17d2ba994de848013b>`;
	typedef std::shared_ptr<:ref:`OpenVINOTensor<doxid-classdlstreamer_1_1_open_v_i_n_o_tensor>`> :target:`OpenVINOTensorPtr<doxid-namespacedlstreamer_1ac468faa0490fd21effccf2436cd98795>`;
	typedef std::shared_ptr<:ref:`Sink<doxid-classdlstreamer_1_1_sink>`> :target:`SinkPtr<doxid-namespacedlstreamer_1aa788e2cb8000621cfb9648dd7d00bec0>`;
	typedef std::shared_ptr<:ref:`Source<doxid-classdlstreamer_1_1_source>`> :target:`SourcePtr<doxid-namespacedlstreamer_1a188a2497b4b06719d2d24197ad5294a4>`;
	typedef std::shared_ptr<:ref:`SYCLContext<doxid-classdlstreamer_1_1_s_y_c_l_context>`> :target:`SYCLContextPtr<doxid-namespacedlstreamer_1aab4aa06a967a45db7a9a782cdcdaa8cd>`;
	typedef std::shared_ptr<:ref:`SYCLUSMTensor<doxid-classdlstreamer_1_1_s_y_c_l_u_s_m_tensor>`> :target:`SYCLUSMTensorPtr<doxid-namespacedlstreamer_1a94967b79500d5403ac809f2cdaec53c4>`;
	typedef std::vector<:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>`> :target:`TensorVector<doxid-namespacedlstreamer_1aef57279f206868573faca2d977200ea9>`;
	typedef std::vector<:ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`> :target:`TensorInfoVector<doxid-namespacedlstreamer_1a6dc9660eef60412db1ceb13fc012734b>`;
	typedef std::shared_ptr<:ref:`Transform<doxid-classdlstreamer_1_1_transform>`> :target:`TransformPtr<doxid-namespacedlstreamer_1a6580e9fce893aa88197fa20240783c9b>`;
	typedef std::unique_ptr<T, std::function<void(T*)>> :target:`auto_ptr<doxid-namespacedlstreamer_1a53305291cab1b066fe310ec8d72b2deb>`;
	typedef std::shared_ptr<:ref:`VAAPIContext<doxid-classdlstreamer_1_1_v_a_a_p_i_context>`> :target:`VAAPIContextPtr<doxid-namespacedlstreamer_1ab6f31ebb8968060d413d39a9c754c07d>`;
	typedef std::shared_ptr<:ref:`VAAPIFrame<doxid-classdlstreamer_1_1_v_a_a_p_i_frame>`> :target:`VAAPIFramePtr<doxid-namespacedlstreamer_1a189caced54d8f866b4cae6be31c76a82>`;
	typedef std::shared_ptr<:ref:`VAAPITensor<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor>`> :target:`VAAPITensorPtr<doxid-namespacedlstreamer_1a0585ca2e3499bf577cfa0c3384a9e1bb>`;

	// enums

	enum :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>`;
	enum :ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>`;
	enum :ref:`ElementFlags<doxid-namespacedlstreamer_1ae8d777fdddec0030ed4811d12c60ec11>`;
	enum :ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>`;
	enum :ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>`;
	enum :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>`;

	// structs

	struct :ref:`AudioFormat<doxid-structdlstreamer_1_1_audio_format>`;
	struct :ref:`AudioInfo<doxid-structdlstreamer_1_1_audio_info>`;
	struct :ref:`ElementDesc<doxid-structdlstreamer_1_1_element_desc>`;
	struct :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`;
	struct :ref:`GstDLStreamerMemory<doxid-structdlstreamer_1_1_gst_d_l_streamer_memory>`;
	struct :ref:`ImageInfo<doxid-structdlstreamer_1_1_image_info>`;
	struct :ref:`ParamDesc<doxid-structdlstreamer_1_1_param_desc>`;
	struct :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`;

	// classes

	class :ref:`AffineTransformInfoMetadata<doxid-classdlstreamer_1_1_affine_transform_info_metadata>`;
	class :ref:`BaseContext<doxid-classdlstreamer_1_1_base_context>`;
	class :ref:`BaseDictionary<doxid-classdlstreamer_1_1_base_dictionary>`;

	template <class T>
	class :ref:`BaseElement<doxid-classdlstreamer_1_1_base_element>`;

	class :ref:`BaseFrame<doxid-classdlstreamer_1_1_base_frame>`;
	class :ref:`BaseMemoryMapper<doxid-classdlstreamer_1_1_base_memory_mapper>`;
	class :ref:`BaseMetadata<doxid-classdlstreamer_1_1_base_metadata>`;
	class :ref:`BaseSink<doxid-classdlstreamer_1_1_base_sink>`;
	class :ref:`BaseSource<doxid-classdlstreamer_1_1_base_source>`;
	class :ref:`BaseTensor<doxid-classdlstreamer_1_1_base_tensor>`;
	class :ref:`BaseTransform<doxid-classdlstreamer_1_1_base_transform>`;
	class :ref:`BaseTransformInplace<doxid-classdlstreamer_1_1_base_transform_inplace>`;

	template <typename T>
	class :ref:`BlockingQueue<doxid-classdlstreamer_1_1_blocking_queue>`;

	class :ref:`CPUContext<doxid-classdlstreamer_1_1_c_p_u_context>`;
	class :ref:`CPUFrameAlloc<doxid-classdlstreamer_1_1_c_p_u_frame_alloc>`;
	class :ref:`CPUTensor<doxid-classdlstreamer_1_1_c_p_u_tensor>`;
	class :ref:`CPUTensorAlloc<doxid-classdlstreamer_1_1_c_p_u_tensor_alloc>`;
	class :ref:`ClassificationMetadata<doxid-classdlstreamer_1_1_classification_metadata>`;
	class :ref:`Context<doxid-classdlstreamer_1_1_context>`;
	class :ref:`DMAContext<doxid-classdlstreamer_1_1_d_m_a_context>`;
	class :ref:`DMATensor<doxid-classdlstreamer_1_1_d_m_a_tensor>`;
	class :ref:`DetectionMetadata<doxid-classdlstreamer_1_1_detection_metadata>`;
	class :ref:`Dictionary<doxid-classdlstreamer_1_1_dictionary>`;
	class :ref:`DictionaryProxy<doxid-classdlstreamer_1_1_dictionary_proxy>`;
	class :ref:`Element<doxid-classdlstreamer_1_1_element>`;
	class :ref:`FFmpegContext<doxid-classdlstreamer_1_1_f_fmpeg_context>`;
	class :ref:`FFmpegFrame<doxid-classdlstreamer_1_1_f_fmpeg_frame>`;
	class :ref:`Frame<doxid-classdlstreamer_1_1_frame>`;
	class :ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>`;
	class :ref:`GSTContext<doxid-classdlstreamer_1_1_g_s_t_context>`;
	class :ref:`GSTContextQuery<doxid-classdlstreamer_1_1_g_s_t_context_query>`;
	class :ref:`GSTDictionary<doxid-classdlstreamer_1_1_g_s_t_dictionary>`;
	class :ref:`GSTFrame<doxid-classdlstreamer_1_1_g_s_t_frame>`;
	class :ref:`GSTFrameBatch<doxid-classdlstreamer_1_1_g_s_t_frame_batch>`;
	class :ref:`GSTMetadata<doxid-classdlstreamer_1_1_g_s_t_metadata>`;
	class :ref:`GSTROIDictionary<doxid-classdlstreamer_1_1_g_s_t_r_o_i_dictionary>`;
	class :ref:`GSTROIMetadata<doxid-classdlstreamer_1_1_g_s_t_r_o_i_metadata>`;
	class :ref:`GSTTensor<doxid-classdlstreamer_1_1_g_s_t_tensor>`;
	class :ref:`ImageLayout<doxid-classdlstreamer_1_1_image_layout>`;
	class :ref:`InferenceResultMetadata<doxid-classdlstreamer_1_1_inference_result_metadata>`;
	class :ref:`LevelZeroContext<doxid-classdlstreamer_1_1_level_zero_context>`;
	class :ref:`MemoryMapper<doxid-classdlstreamer_1_1_memory_mapper>`;
	class :ref:`MemoryMapperAnyToGST<doxid-classdlstreamer_1_1_memory_mapper_any_to_g_s_t>`;
	class :ref:`MemoryMapperCPUToOpenCV<doxid-classdlstreamer_1_1_memory_mapper_c_p_u_to_open_c_v>`;
	class :ref:`MemoryMapperCPUToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_c_p_u_to_open_v_i_n_o>`;
	class :ref:`MemoryMapperCache<doxid-classdlstreamer_1_1_memory_mapper_cache>`;
	class :ref:`MemoryMapperChain<doxid-classdlstreamer_1_1_memory_mapper_chain>`;
	class :ref:`MemoryMapperDMAToOpenCL<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_open_c_l>`;
	class :ref:`MemoryMapperDMAToUSM<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_u_s_m>`;
	class :ref:`MemoryMapperDMAToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_d_m_a_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperFFMPEGToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_f_f_m_p_e_g_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperGSTToDMA<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_d_m_a>`;
	class :ref:`MemoryMapperGSTToOpenCL<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_open_c_l>`;
	class :ref:`MemoryMapperGSTToVAAPI<doxid-classdlstreamer_1_1_memory_mapper_g_s_t_to_v_a_a_p_i>`;
	class :ref:`MemoryMapperOpenCLToCPU<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_c_p_u>`;
	class :ref:`MemoryMapperOpenCLToDMA<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_d_m_a>`;
	class :ref:`MemoryMapperOpenCLToOpenCVUMat<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_open_c_v_u_mat>`;
	class :ref:`MemoryMapperOpenCLToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_open_c_l_to_open_v_i_n_o>`;
	class :ref:`MemoryMapperOpenVINOToCPU<doxid-classdlstreamer_1_1_memory_mapper_open_v_i_n_o_to_c_p_u>`;
	class :ref:`MemoryMapperSYCLUSMToCPU<doxid-classdlstreamer_1_1_memory_mapper_s_y_c_l_u_s_m_to_c_p_u>`;
	class :ref:`MemoryMapperUSMToDMA<doxid-classdlstreamer_1_1_memory_mapper_u_s_m_to_d_m_a>`;
	class :ref:`MemoryMapperVAAPIToDMA<doxid-classdlstreamer_1_1_memory_mapper_v_a_a_p_i_to_d_m_a>`;
	class :ref:`MemoryMapperVAAPIToOpenVINO<doxid-classdlstreamer_1_1_memory_mapper_v_a_a_p_i_to_open_v_i_n_o>`;
	class :ref:`Metadata<doxid-classdlstreamer_1_1_metadata>`;
	class :ref:`ModelInfoMetadata<doxid-classdlstreamer_1_1_model_info_metadata>`;
	class :ref:`ObjectIdMetadata<doxid-classdlstreamer_1_1_object_id_metadata>`;
	class :ref:`OpenCLContext<doxid-classdlstreamer_1_1_open_c_l_context>`;
	class :ref:`OpenCLTensor<doxid-classdlstreamer_1_1_open_c_l_tensor>`;
	class :ref:`OpenCLTensorRefCounted<doxid-classdlstreamer_1_1_open_c_l_tensor_ref_counted>`;
	class :ref:`OpenCVContext<doxid-classdlstreamer_1_1_open_c_v_context>`;
	class :ref:`OpenCVTensor<doxid-classdlstreamer_1_1_open_c_v_tensor>`;
	class :ref:`OpenCVUMatContext<doxid-classdlstreamer_1_1_open_c_v_u_mat_context>`;
	class :ref:`OpenCVUMatTensor<doxid-classdlstreamer_1_1_open_c_v_u_mat_tensor>`;
	class :ref:`OpenVINOContext<doxid-classdlstreamer_1_1_open_v_i_n_o_context>`;
	class :ref:`OpenVINOFrame<doxid-classdlstreamer_1_1_open_v_i_n_o_frame>`;
	class :ref:`OpenVINOTensor<doxid-classdlstreamer_1_1_open_v_i_n_o_tensor>`;
	class :ref:`OpenVINOTensorBatch<doxid-classdlstreamer_1_1_open_v_i_n_o_tensor_batch>`;

	template <typename T>
	class :ref:`Pool<doxid-classdlstreamer_1_1_pool>`;

	class :ref:`SYCLContext<doxid-classdlstreamer_1_1_s_y_c_l_context>`;
	class :ref:`SYCLUSMTensor<doxid-classdlstreamer_1_1_s_y_c_l_u_s_m_tensor>`;
	class :ref:`Sink<doxid-classdlstreamer_1_1_sink>`;
	class :ref:`Source<doxid-classdlstreamer_1_1_source>`;
	class :ref:`SourceIdentifierMetadata<doxid-classdlstreamer_1_1_source_identifier_metadata>`;
	class :ref:`Tensor<doxid-classdlstreamer_1_1_tensor>`;
	class :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>`;
	class :ref:`TimestampMetadata<doxid-classdlstreamer_1_1_timestamp_metadata>`;
	class :ref:`Transform<doxid-classdlstreamer_1_1_transform>`;
	class :ref:`TransformInplace<doxid-classdlstreamer_1_1_transform_inplace>`;
	class :ref:`USMTensor<doxid-classdlstreamer_1_1_u_s_m_tensor>`;
	class :ref:`VAAPIContext<doxid-classdlstreamer_1_1_v_a_a_p_i_context>`;
	class :ref:`VAAPIFrame<doxid-classdlstreamer_1_1_v_a_a_p_i_frame>`;
	class :ref:`VAAPIFrameAlloc<doxid-classdlstreamer_1_1_v_a_a_p_i_frame_alloc>`;
	class :ref:`VAAPITensor<doxid-classdlstreamer_1_1_v_a_a_p_i_tensor>`;

	// global variables

	static constexpr int32_t :target:`ElementDescMagic<doxid-namespacedlstreamer_1a4945e41baded9f9a6a5c2c7e25c1e0c7>` = 0x34495239;
	static constexpr static GstMapFlags :target:`GST_MAP_NATIVE_HANDLE<doxid-namespacedlstreamer_1a37bc58b93336eec44c00034d0cedb63b>` = static_cast<GstMapFlags>(GST_MAP_FLAG_LAST<<1);

	// global functions

	static :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>` :target:`squeeze_tensor_info<doxid-namespacedlstreamer_1af7a2ea3aad0ca095d0fb041346bf580c>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info);

	static :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :target:`get_tensor_slice<doxid-namespacedlstreamer_1a86ded495d308373e4b712cd3f01ed209>`(
		:ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` tensor,
		const std::vector<std::pair<size_t, size_t>>& slice,
		bool squeeze = false
	);

	template <typename T>
	T :target:`any_cast<doxid-namespacedlstreamer_1ab0c9c65e3507c1380b0f550e4e2d86df>`(const :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`& any);

	template <typename T>
	bool :target:`any_holds_type<doxid-namespacedlstreamer_1ac2651b21f764020fb6a7b0db04ac1e58>`(const :ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`& any);

	template <class Ty>
	static :ref:`Element<doxid-classdlstreamer_1_1_element>`* :target:`create_element<doxid-namespacedlstreamer_1a97fd94335d311fb5170502f1213e5ef8>`(
		:ref:`DictionaryCPtr<doxid-namespacedlstreamer_1a8407dcbf0aebfcb357acad3ac2d27bfc>` params,
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context
	);

	:ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` :target:`avformat_to_image_format<doxid-namespacedlstreamer_1aae1e74f3e7278d1c375a5bced6484fbb>`(int format);
	:ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`avframe_to_info<doxid-namespacedlstreamer_1a641296fed0b98f648de0354e03fdcbb9>`(AVFrame* frame);
	G_BEGIN_DECLS GstAllocator* :target:`gst_dlstreamer_allocator_new<doxid-namespacedlstreamer_1a2b9efcdbda16dde4402f832fd8855043>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);

	GstMemory* :target:`gst_dlstreamer_allocator_wrap_tensor<doxid-namespacedlstreamer_1a38e6756da4ab44528878bd53030a0c0d>`(
		GstAllocator* allocator,
		const :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>`& tensor
	);

	gboolean :target:`gst_is_dlstreamer_memory<doxid-namespacedlstreamer_1a4eebdf0832c4011481dc7d8cb4f33bf4>`(GstMemory* mem);
	G_END_DECLS :ref:`TensorPtr<doxid-classdlstreamer_1_1_tensor_ptr>` :target:`gst_dlstreamer_memory_get_tensor_ptr<doxid-namespacedlstreamer_1aed90f5e1720d44f515e0b8a035404913>`(GstMemory* mem);
	static :ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` :target:`gst_format_to_video_format<doxid-namespacedlstreamer_1a5f9ded0845f1ddbeb803f5d759e154a7>`(int format);
	static GstVideoFormat :target:`video_format_to_gst_format<doxid-namespacedlstreamer_1ac7d8a5bdbab5ff93bca4142e276ad093>`(:ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` format);
	static :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`gst_video_info_to_frame_info<doxid-namespacedlstreamer_1a895e170293538acf3f00a633c3b4e9fa>`(const GstVideoInfo* vinfo);
	static GstCapsFeatures* :target:`memory_type_to_gst_caps_feature<doxid-namespacedlstreamer_1ab323b8a5f28515730c15199d078965e6>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` memory_type);
	static GstCaps* :target:`frame_info_to_gst_caps<doxid-namespacedlstreamer_1a364ab6f72c1873f7044c293e60e77937>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& info);
	static GstCaps* :target:`frame_info_vector_to_gst_caps<doxid-namespacedlstreamer_1adb6c16dc28a4347eab3914e462e86ed2>`(const :ref:`FrameInfoVector<doxid-namespacedlstreamer_1ad9841a81bbd2afc2c172b7df8f575a80>`& infos);
	static :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`gst_caps_to_frame_info<doxid-namespacedlstreamer_1a5665058b880657645d938addab95fed7>`(const GstCaps* caps, guint index = 0);
	static :ref:`AccessMode<doxid-namespacedlstreamer_1a688aea01f1e852531b035128bbea9e10>` :target:`gst_map_flags_to_access_mode<doxid-namespacedlstreamer_1a4f415c809c4079fd4aaffb77e26b6bd7>`(GstMapFlags flags);

	static std::optional<:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>`> :target:`gvalue_to_any<doxid-namespacedlstreamer_1a12225bf60e288e2ac84795e291d73cef>`(
		const GValue* gval,
		const :ref:`ParamDesc<doxid-structdlstreamer_1_1_param_desc>`* desc = nullptr
	);

	static void :target:`any_to_gvalue<doxid-namespacedlstreamer_1ac0b31911d085c8a5be04eedc87eae143>`(
		:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value,
		GValue* gvalue,
		bool init = true,
		const :ref:`ParamDesc<doxid-structdlstreamer_1_1_param_desc>`* desc = nullptr
	);

	template <typename T>
	static std::vector<T> :target:`gvalue_to_vector<doxid-namespacedlstreamer_1aa00b33c6f32daf46930ebe4949248426>`(const GValue* value);

	template <typename T>
	static void :target:`vector_to_gvalue<doxid-namespacedlstreamer_1ae0fce3795ccc4a0e113113f7cff8dcee>`(
		std::vector<T> vec,
		GValue* gvalue
	);

	static GParamSpec* :target:`param_desc_to_spec<doxid-namespacedlstreamer_1a6d8e05cb9484b23c93de595143f11ea3>`(
		const :ref:`ParamDesc<doxid-structdlstreamer_1_1_param_desc>`& param,
		GstStructure* enums_storage
	);

	static std::string :target:`get_property_as_string<doxid-namespacedlstreamer_1a8ebf5d10cc86c8524a940a4510dba404>`(GObject* object, const gchar* name);
	static std::string :target:`image_format_to_string<doxid-namespacedlstreamer_1a2de1ab6f00d5b80d92aeed5bba2fd3b0>`(:ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` format);

	static :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` :ref:`create_mapper<doxid-namespacedlstreamer_1ab5c22570d8b24704bc18334687b55012>`(
		std::vector<:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`> context_chain,
		bool use_cache = false
	);

	template <typename T_DOWN, typename T_UP>
	static std::shared_ptr<T_DOWN> :target:`ptr_cast<doxid-namespacedlstreamer_1a5e78b5546846d6e89765e299cf8b65d6>`(const std::shared_ptr<T_UP>& ptr_up);

	const char* :target:`memory_type_to_string<doxid-namespacedlstreamer_1af56c1fcc59434cbd3437a58c2fea0f09>`(:ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` type);
	static :ref:`MemoryType<doxid-namespacedlstreamer_1adf13505dedb784c9027f629e8e97f1db>` :target:`memory_type_from_string<doxid-namespacedlstreamer_1a76f6273c2eb45a00643f37053be666f0>`(std::string str);
	cl_channel_order :target:`num_channels_to_opencl<doxid-namespacedlstreamer_1a25d676c7e11bd1f73f11d77bebfe4580>`(int channels);
	cl_channel_type :target:`data_type_to_opencl<doxid-namespacedlstreamer_1a0e808b36812acf84f43d096de6f7c328>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` type);
	static int :target:`data_type_to_opencv<doxid-namespacedlstreamer_1a792a2da7dadd92c17879c80873eb4bdb>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` type);
	static :ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` :target:`data_type_from_openvino<doxid-namespacedlstreamer_1a98d0dc3468bd4a5e6e20bd57e468535c>`(ov::element::Type element);
	static ov::element::Type :target:`data_type_to_openvino<doxid-namespacedlstreamer_1aa8c7db6a9d5e75c3b984f1eaabf19bf1>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` type);
	static :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>` :target:`ov_tensor_to_tensor_info<doxid-namespacedlstreamer_1a5c113df9d2c45daebfb8061a5abe6b6e>`(ov::Tensor tensor);

	static :ref:`SinkPtr<doxid-namespacedlstreamer_1aa788e2cb8000621cfb9648dd7d00bec0>` :target:`create_sink<doxid-namespacedlstreamer_1a817566a40b776144f7a343af449d7c5d>`(
		const :ref:`ElementDesc<doxid-structdlstreamer_1_1_element_desc>`& desc,
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	template <class Ty>
	static std::unique_ptr<Ty> :target:`create_sink<doxid-namespacedlstreamer_1a0f4bf6f3609c1d6f259563c1f45f1f30>`(
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	static :ref:`SourcePtr<doxid-namespacedlstreamer_1a188a2497b4b06719d2d24197ad5294a4>` :target:`create_source<doxid-namespacedlstreamer_1adb8f0f6bcad8984542423f07eec92330>`(
		const :ref:`ElementDesc<doxid-structdlstreamer_1_1_element_desc>`& desc,
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	template <class Ty>
	static std::unique_ptr<Ty> :target:`create_source<doxid-namespacedlstreamer_1a50267b818bff2154a003e5054d3ab1be>`(
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	static size_t :target:`datatype_size<doxid-namespacedlstreamer_1ae577fbcdcfa9f0cb6b5acac8c24fd0e3>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` datatype);

	static std::vector<size_t> :target:`contiguous_stride<doxid-namespacedlstreamer_1a1c3d84ad285a42ec3d3c930cd9c285ed>`(
		const std::vector<size_t>& shape,
		:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` type
	);

	template <typename T>
	bool :target:`check_datatype<doxid-namespacedlstreamer_1ad83c0c90f03cfc9b4d822dcc5b8daa29>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>`);

	bool :target:`check_datatype< uint8_t ><doxid-namespacedlstreamer_1a8a8a38a1de5de4e7edff2f412eb427fa>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` dtype);
	bool :target:`check_datatype< int32_t ><doxid-namespacedlstreamer_1a7c2fd59626284e312ab27d5080228187>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` dtype);
	bool :target:`check_datatype< int64_t ><doxid-namespacedlstreamer_1ac7cce0cc1bf970afd1dca5dc1b16bf7f>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` dtype);
	bool :target:`check_datatype< float ><doxid-namespacedlstreamer_1a7622ac160ea821e20215a851f52a6699>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` dtype);

	static :ref:`TransformPtr<doxid-namespacedlstreamer_1a6580e9fce893aa88197fa20240783c9b>` :target:`create_transform<doxid-namespacedlstreamer_1a66ba9aa2d9f8d9d3195aeb5ddea46a19>`(
		const :ref:`ElementDesc<doxid-structdlstreamer_1_1_element_desc>`& desc,
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	template <class Ty>
	static std::unique_ptr<Ty> :target:`create_transform<doxid-namespacedlstreamer_1a1820e26ca860af800f3333d37574da51>`(
		const :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`& params = :ref:`AnyMap<doxid-namespacedlstreamer_1a655f61b1cf16bd014b1faf20046dc518>`(),
		const :ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`& app_context = nullptr
	);

	static :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>` :target:`frame_info<doxid-namespacedlstreamer_1ac36f235232a97a5aedd67f37ab909548>`(:ref:`FramePtr<doxid-classdlstreamer_1_1_frame_ptr>` frame);

	static std::vector<std::string> :target:`split_string<doxid-namespacedlstreamer_1abec726a8fdcefe5929a462e79c7aca8e>`(
		const std::string& input,
		char delimiter = ','
	);

	template <typename OUTPUT, typename INPUT, typename O>
	static std::vector<OUTPUT> :target:`transform_vector<doxid-namespacedlstreamer_1aa964716a172bdf755a1100c1bc0349c6>`(
		const std::vector<INPUT>& input,
		O op
	);

	template <typename Iter>
	static std::string :target:`join_strings<doxid-namespacedlstreamer_1a033576b4a266d94f73ef03eb97ce994a>`(
		Iter begin,
		Iter end,
		char delimiter = ','
	);

	static :ref:`DictionaryPtr<doxid-namespacedlstreamer_1ab94d4f1fc850dbd9c71343191460d20a>` :target:`find_metadata<doxid-namespacedlstreamer_1a2b638ada96e1b3e6ac1da43d77e8ee1f>`(
		const :ref:`Frame<doxid-classdlstreamer_1_1_frame>`& frame,
		std::string_view meta_name
	);

	template <class T>
	static std::shared_ptr<T> :target:`find_metadata<doxid-namespacedlstreamer_1a323dc4d6c1d411035d9f4b329ab8867e>`(
		const :ref:`Frame<doxid-classdlstreamer_1_1_frame>`& frame,
		std::string_view meta_name,
		std::string_view format
	);

	template <class T>
	static T :target:`add_metadata<doxid-namespacedlstreamer_1aa0a6ab498abc8738b37b2125253a66be>`(
		:ref:`Frame<doxid-classdlstreamer_1_1_frame>`& frame,
		std::string_view meta_name = T::name
	);

	static void :target:`copy_dictionary<doxid-namespacedlstreamer_1a8e95ac5a6e80d8fe1c68e9353a732507>`(
		const :ref:`Dictionary<doxid-classdlstreamer_1_1_dictionary>`& src,
		:ref:`Dictionary<doxid-classdlstreamer_1_1_dictionary>`& dst,
		bool copy_name = false
	);

	static void :target:`copy_metadata<doxid-namespacedlstreamer_1a72ab49c4ca98bbc8acb731395c10c029>`(const :ref:`Frame<doxid-classdlstreamer_1_1_frame>`& src, :ref:`Frame<doxid-classdlstreamer_1_1_frame>`& dst);
	static std::string :target:`any_to_string<doxid-namespacedlstreamer_1aed80c96f5f21992dd63a1ad0e210a8f5>`(:ref:`Any<doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4>` value);
	static std::string :target:`datatype_to_string<doxid-namespacedlstreamer_1aed82d1279b4aecc9827d0cca9cef80e5>`(:ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` datatype);
	static :ref:`DataType<doxid-namespacedlstreamer_1a7a7492b0df5cc3ad654a97cd54502d82>` :target:`datatype_from_string<doxid-namespacedlstreamer_1ab49213151d46fd89dfc6f6f1a2b4fab6>`(const std::string& str);
	static std::string :target:`media_type_to_string<doxid-namespacedlstreamer_1a2ba8573cc867d917930079b3b55ec0fd>`(:ref:`MediaType<doxid-namespacedlstreamer_1aa880cf952e5b844d472f66d51efa3707>` media_type);
	static std::vector<size_t> :target:`shape_from_string<doxid-namespacedlstreamer_1ac0511fc212372d00f7e1075844ecfe79>`(const std::string& str);
	static std::string :target:`shape_to_string<doxid-namespacedlstreamer_1af1a0826c12ddfb389a1d8eaf8e58a49b>`(const std::vector<size_t>& dims);
	static std::string :target:`tensor_info_to_string<doxid-namespacedlstreamer_1ae3c9aaf2d209d520fb0c81898df42004>`(const :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>`& info);
	static :ref:`TensorInfo<doxid-structdlstreamer_1_1_tensor_info>` :target:`tensor_info_from_string<doxid-namespacedlstreamer_1ac1f7357757c447b6e1604c81c142c07a>`(const std::string& str);
	static std::string :target:`frame_info_to_string<doxid-namespacedlstreamer_1a01bc5a10f3534a3f890c77d8eb084927>`(const :ref:`FrameInfo<doxid-structdlstreamer_1_1_frame_info>`& finfo);
	static uint32_t :target:`video_format_to_vaapi<doxid-namespacedlstreamer_1a17f2205862aeaeb16b86fdcab7c7f48e>`(:ref:`ImageFormat<doxid-namespacedlstreamer_1a335d5fffc58016aeb44c15b058f56466>` format);
	static uint32_t :target:`vaapi_video_format_to_rtformat<doxid-namespacedlstreamer_1a104094492bb4546cb7f7d705157a5f47>`(uint32_t video_format);

	} // namespace dlstreamer
.. _details-namespacedlstreamer:

Detailed Documentation
~~~~~~~~~~~~~~~~~~~~~~



Typedefs
--------

.. index:: pair: typedef; Any
.. _doxid-namespacedlstreamer_1ab7893a9ae168d5251d6a85330aea0bc4:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	typedef std::variant<int, double, size_t, std::string, std::vector<int>, std::vector<double>, std::vector<size_t>, std::vector<std::string>, intptr_t, bool, std::pair<int, int>> Any

Type-safe union of selective basic types (defined via std::variant, requires C++17).

Global Functions
----------------

.. index:: pair: function; create_mapper
.. _doxid-namespacedlstreamer_1ab5c22570d8b24704bc18334687b55012:

.. ref-code-block:: cpp
	:class: doxyrest-title-code-block

	static :ref:`MemoryMapperPtr<doxid-namespacedlstreamer_1a6e9a7ff17b4ff02042f7ad6784323f10>` create_mapper(
		std::vector<:ref:`ContextPtr<doxid-namespacedlstreamer_1a2eba287f35b2698b87aa6f560299ffe8>`> context_chain,
		bool use_cache = false
	)

Creates chain of memory mappers as requested by vector of ContextPtr objects, and returns mapper object with input context equal to first element in specified vector and output context equal to last element in specified vector of context objects.



.. rubric:: Parameters:

.. list-table::
	:widths: 20 80

	*
		- context_chain

		- Vector of context objects defining mapping sequence

	*
		- use_cache

		- If true, the returned mapper cashes internally all mapped :ref:`TensorPtr <doxid-classdlstreamer_1_1_tensor_ptr>` and :ref:`FramePtr <doxid-classdlstreamer_1_1_frame_ptr>` objects to avoid mapping operation on same TensorPtr/FramePtr multiple times. This optimization is useful for case mapper works on pool of limited number TensorPtr/FramePtr objects.

