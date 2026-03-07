# 语言驱动的视频生成方法
大创项目“语言驱动的视频生成方法”。利用文生图模型指导wan2.1视频生成模型进行视频生成，从而实现各种风格的更高质量视频的生成。

在本仓库中，我们制作了几个ComfyUI工作流。这些工作流提供了将文生图模型与图生视频结合，从而生成质量更高的各种人物风格视频的功能。此外，我们尽量减少了运行时占用的内存与GPU，使该工作流可以在个人计算机上运行。


## 工作流使用示例
### 1.模型下载
我们选择了wan2.1作为我们的图生视频模型。该模型占用显存较小，可以在消费级显卡上运行。同时该模型视频生成质量较好，并提供了多种可选择的分辨率。

[**Wan2.1**](https://github.com/Wan-Video/Wan2.1)

请根据需要下载以下模型或模型的其他版本

**Diffusion models**

- [**wan2.1_i2v_720p_14B_fp8_e4m3fn.safetensors**](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/resolve/main/split_files/diffusion_models/wan2.1_i2v_720p_14B_fp8_e4m3fn.safetensors?download=true)

- [**wan2.1_i2v_480p_14B_fp8_e4m3fn.safetensors**](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/resolve/main/split_files/diffusion_models/wan2.1_i2v_480p_14B_fp8_e4m3fn.safetensors?download=true)

**Text encoders**

- [**umt5_xxl_fp8_e4m3fn_scaled.safetensors**](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/resolve/main/split_files/text_encoders/umt5_xxl_fp8_e4m3fn_scaled.safetensors?download=true)

**VAE**

- [**wan_2.1_vae.safetensors**](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/resolve/main/split_files/vae/wan_2.1_vae.safetensors?download=true)

**CLIP Vision**

- [**clip_vision_h.safetensors**](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/resolve/main/split_files/clip_vision/clip_vision_h.safetensors?download=true)

<br/>

你可以选择任何你喜欢的文生图模型。在默认的工作流中，我们使用了**Nova Anime XL**作为我们的文生图模型，以获得更好的动漫人物形象生成效果

- [**novaAnimeXL_ilV140.safetensors**](https://civitai.com/api/download/models/2741698?type=Model&format=SafeTensor&size=pruned&fp=fp16)

### 2.完成参数与模型设置

