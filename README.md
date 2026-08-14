![](https://img.shields.io/github/release/shadowcz007/comfyui-mixlab-nodes)

> 适配了最新版 comfyui 的 py3.11 ，torch 2.3.1+cu121
> [Mixlab nodes discord](https://discord.gg/cXs9vZSqeK)

商务合作请联系 389570357@qq.com
For business cooperation, please contact email 389570357@qq.com

![Her 的DEMO页面](assets/1725710761451.png)

##### `最新`：

- 新增[fal.ai](https://fal.ai/dashboard)的视频生成:Kling、RunwayGen3、LumaDreamMachine，[工作流下载](./workflow/video-all-in-one-test-workflow.json)

- 新增 SimulateDevDesignDiscussions，需要安装[swarm](https://github.com/openai/swarm)和[Comfyui-ChatTTS](https://github.com/shadowcz007/Comfyui-ChatTTS)，[工作流下载](./workflow/swarm制作的播客节点workflow.json)

- 新增 SenseVoice

- [新增JS-SDK，方便直接在前端项目中使用comfyui](https://github.com/shadowcz007/comfyui-js-sdk)

- 新增API调用图像生成节点 TextToImage Siliconflow，可以直接调用Siliconflow提供的flux生成图像

- [增加 Her 的DEMO页面，和数字人对话](https://github.com/shadowcz007/ComfyUI-Backend-MixlabNodes/blob/main/workflow/her_demo_workflow.json)

- 右键菜单支持 text-to-text，方便对 prompt 词补全，支持云LLM或者是本地LLM。

- 增加 MiniCPM-V 2.6 int4

This is the int4 quantized version of MiniCPM-V 2.6.
Running with int4 version would use lower GPU memory (about 7GB).

- 移动端适配、修改 app 模式的 Mask 编辑器

- 增加 p5.js 作为输入节点
  [workflow](./workflow/p5workflow.json)
  [workflow2](./workflow/p5-video-workflow.json)

- App 模式增加 batch prompt，批量提示词，可以把动态提示词批量组成后运行

![alt text](./assets/1722517810720.png)

- 增加 API Key Input 节点，用于管理 LLM 的 Key,同时优化 LLM 相关节点，为后续 agent 模式做准备

- 增加 SiliconflowLLM，可以使用由 Siliconflow 提供的免费 LLM

<!-- - ChatGPT 节点支持 Local LLM（llama.cpp），Phi3、llama3 都可以直接一个节点运行了。模型下载后，放置到 `models/llamafile/` -->

<!--
强烈推荐：
[Phi-3-mini-4k-instruct-function-calling-GGUF](https://huggingface.co/nold/Phi-3-mini-4k-instruct-function-calling-GGUF)

[Phi-3-mini-4k-instruct-GGUF](https://huggingface.co/lmstudio-community/Phi-3-mini-4k-instruct-GGUF/tree/main)，备选：[llama3_if_ai_sdpromptmkr_q2k](https://hf-mirror.com/impactframes/llama3_if_ai_sdpromptmkr_q2k/tree/main)

- 右键菜单支持 image-to-text，使用多模态模型，多模态使用 [llava-phi-3-mini-gguf](https://huggingface.co/xtuner/llava-phi-3-mini-gguf/tree/main)，注意需要把llava-phi-3-mini-mmproj-f16.gguf也下载

![](./assets/prompt_ai_setup.png)
![](./assets/prompt-ai.png) -->

#### `相关插件推荐`

[comfyui-liveportrait](https://github.com/shadowcz007/comfyui-liveportrait)

[Comfyui-ChatTTS](https://github.com/shadowcz007/Comfyui-ChatTTS)

[comfyui-sound-lab](https://github.com/shadowcz007/comfyui-sound-lab)

[comfyui-Image-reward](https://github.com/shadowcz007/comfyui-Image-reward)

[comfyui-ultralytics-yolo](https://github.com/shadowcz007/comfyui-ultralytics-yolo)

[comfyui-moondream](https://github.com/shadowcz007/comfyui-moondream)

<!-- [comfyui-CLIPSeg](https://github.com/shadowcz007/comfyui-CLIPSeg) -->

## 🚀🚗🚚🏃 Workflow-to-APP

- 新增 AppInfo 节点，可以通过简单的配置，把 workflow 转变为一个 Web APP。
- 支持多个 web app 切换
- 发布为 app 的 workflow，可以在右键里再次编辑了
- web app 可以设置分类，在 comfyui 右键菜单可以编辑更新 web app
- 支持动态提示
- 支持把输出显示到 comfyui 背景（TouchDesigner 风格）
- 如果转为 web app 打开是空白的，注意检查下插件目录的名字需要是：comfyui-mixlab-nodes(如果是 zip 包下载会多了个-main 的后缀，需要去掉)

![](./assets/微信图片_20240421205440.png)

- Support multiple web app switching.
- Add the AppInfo node, which allows you to transform the workflow into a web app by simple configuration.
- The workflow, which is now released as an app, can also be edited again by right-clicking.
- The web app can be configured with categories, and the web app can be edited and updated in the right-click menu of ComfyUI.

![](./assets/0-m-app.png)

![](./assets/appinfo-readme.png)

![](./assets/appinfo-2.png)

Example:

- workflow
  ![APP info](./workflow/appinfo-workflow.svg)
  [text-to-image](./workflow/Text-to-Image-app.json)

APP-JSON:

- [text-to-image](./example/Text-to-Image_3.json)
- [image-to-image](./example/Image-to-Image_2.json)
- text-to-text

> 暂时支持 9 种节点作为界面上的输入节点：Load Image、VHS*LoadVideo、CLIPTextEncode、PromptSlide、TextInput*、Color、FloatSlider、IntNumber、CheckpointLoaderSimple、LoraLoader

> 输出节点：PreviewImage 、SaveImage、ShowTextForGPT、VHS_VideoCombine、PromptImage

> seed 统一输入控件，支持：SamplerCustom、KSampler

> 配套[ps 插件](https://github.com/shadowcz007/comfyui-ps-plugin)

> 如果遇到上传图片不成功，请检查下：局域网或者是云服务，请使用 https，端口 8189 这个服务（ 感谢 @Damien 反馈问题）

> If you encounter difficulties in uploading images, please check the following: for local network or cloud services, please use HTTPS and the service on port 8189. (Thanks to @Damien for reporting the issue.)

## 🏃🚗🚚🚀 Real-time Design

> ScreenShareNode & FloatingVideoNode. Now comfyui supports capturing screen pixel streams from any software and can be used for LCM-Lora integration. Let's get started with implementation and design! 💻🌐

![screenshare](./assets/screenshare.png)

https://github.com/shadowcz007/comfyui-mixlab-nodes/assets/12645064/e7e77f90-e43e-410a-ab3a-1952b7b4e7da

<!-- [ScreenShareNode](./workflow/2-screeshare.json) -->

[ScreenShareNode & FloatingVideoNode](./workflow/3-FloatVideo-workflow.json)

!! Please use the address with HTTPS (https://127.0.0.1).

### SpeechRecognition & SpeechSynthesis

![f](./assets/audio-workflow.svg)

[Voice + Real-time Face Swap Workflow](./workflow/语音+实时换脸workflow.json)

- Preview Audio

[text-to-audio](./workflow/text-to-audio-base-workflow.json)

### GPT

> Support for calling multiple GPTs.Local LLM 、 ChatGPT、ChatGLM3 、ChatGLM4 , Some code provided by rui. If you are using OpenAI's service, fill in https://api.openai.com/v1 . If you are using a local LLM service, fill in http://127.0.0.1:xxxx/v1 . Azure OpenAI:https://xxxx.openai.azure.com

[LLM_base_workflow](./workflow/LLM_base_workflow.json)

- SiliconflowLLM
- ChatGPTOpenAI

<!-- 最新：ChatGPT 节点支持 Local LLM（llama.cpp），Phi3、llama3 都可以直接一个节点运行了。

Model download,move to :`models/llamafile/`

强烈推荐：[Phi-3-mini-4k-instruct-GGUF](https://huggingface.co/lmstudio-community/Phi-3-mini-4k-instruct-GGUF/tree/main)

备选：[llama3_if_ai_sdpromptmkr_q2k](https://hf-mirror.com/impactframes/llama3_if_ai_sdpromptmkr_q2k/tree/main)

> 如果碰到安装失败，可以尝试手动安装

```
../../../python_embeded/python.exe -s -m pip install llama-cpp-python --extra-index-url https://abetlen.github.io/llama-cpp-python/whl/cu121

../../../python_embeded/python.exe -s -m pip install llama-cpp-python[server]

```

> [Mac](https://llama-cpp-python.readthedocs.io/en/latest/install/macos/)

```
pip uninstall llama-cpp-python -y
CMAKE_ARGS="-DLLAMA_METAL=on" pip install -U llama-cpp-python --no-cache-dir
pip install 'llama-cpp-python[server]'
```

```
pip install llama-cpp-python \
  --extra-index-url https://abetlen.github.io/llama-cpp-python/whl/metal
``` -->

## Prompt

> PromptSlide
> ![](./assets/prompt_weight.png)

<!-- ![](./workflow/promptslide-appinfo-workflow.svg) -->

> randomPrompt

![randomPrompt](./assets/randomPrompt.png)

> ClipInterrogator

[add clip-interrogator](https://github.com/pharmapsychotic/clip-interrogator)

> PromptImage & PromptSimplification,Assist in simplifying prompt words, comparing images and prompt word nodes.

> ChinesePrompt && PromptGenerate，中文 prompt 节点，直接用中文书写你的 prompt

![](./assets/ChinesePrompt_workflow.svg)

### Layers

> A new layer class node has been added, allowing you to separate the image into layers. After merging the images, you can input the controlnet for further processing.

> The composite images node overlays a foreground image onto a background image at specified positions and scales, with optional blending modes and masking capabilities. position : 'overall',"center_center","left_bottom","center_bottom","right_bottom","left_top","center_top","right_top"

![layers](./assets/layers-workflow.svg)

![poster](./assets/poster-workflow.svg)

### 3D

![](./assets/3d-workflow.png)
![](./assets/3d_app.png)
[workflow](./assets/Image-to-3D_1.json)

![](./assets/3dimage.png)
[workflow](./workflow/3D-workflow.json)

### Image

#### LoadImagesToBatch

> Upload multiple images for batch input into the IP adapter.

#### LoadImagesFromLocal

> Monitor changes to images in a local folder, and trigger real-time execution of workflows, supporting common image formats, especially PSD format, in conjunction with Photoshop.

![watch](./assets/4-loadfromlocal-watcher-workflow.svg)

[workflow-4](./workflow/4-loadfromlocal-watcher-workflow.json)

#### LoadImagesFromURL

> Conveniently load images from a fixed address on the internet to ensure that default images in the workflow can be executed.

#### TextImage

> [下载字体](https://drxie.github.io/OSFCC/)放到 `custom_nodes/comfyui-mixlab-nodes/assets/fonts`

#### MiniCPM-VQA Simple

This is the int4 quantized version of MiniCPM-V 2.6.
Running with int4 version would use lower GPU memory (about 7GB).

[模型](https://huggingface.co/openbmb/MiniCPM-V-2_6-int4)

![alt text](assets/1724308322276.png)

### Style

> Apply VisualStyle Prompting , Modified from [ComfyUI_VisualStylePrompting](https://github.com/ExponentialML/ComfyUI_VisualStylePrompting)

![](./assets/VisualStylePrompting.png)

> StyleAligned , Modified from [style_aligned_comfy](https://github.com/brianfitzgerald/style_aligned_comfy)

### Utils

> The Color node provides a color picker for easy color selection, the Font node offers built-in font selection for use with TextImage to generate text images, and the DynamicDelayByText node allows delayed execution based on the length of the input text.

- [添加了 DynamicDelayByText 功能，可以根据输入文本的长度进行延迟执行。](./workflow/audio-chatgpt-workflow.json)

- [Added DynamicDelayByText, enabling delayed execution based on input text length.](./workflow/audio-chatgpt-workflow.json)

- [使用 CkptNames 对比不同的模型效果](./workflow/ckpts-image-workflow.json)

- [CkptNames compare the effects of different models.](./workflow/ckpts-image-workflow.json)

### Other Nodes

- 增加 Edit Mask，方便在生成的时候手动绘制 mask [workflow](./workflow/edit-mask-workflow.json)

![main](./assets/all-workflow.svg)
![main2](./assets/detect-face-all.png)

[workflow-1](./workflow/1-workflow.json)

> TransparentImage

![TransparentImage](./assets/TransparentImage.png)

> FeatheredMask、SmoothMask

Add edges to an image.

![FeatheredMask](./assets/FlVou_Y6kaGWYoEj1Tn0aTd4AjMI.jpg)

> LaMaInpainting（需要手动安装）

- simple-lama-inpainting 里的 pillow 造成冲突，暂时从依赖里移除，如果有安装 simple-lama-inpainting ，节点会自动添加，没有，则不会自动添加。

from [simple-lama-inpainting](https://github.com/enesmsahin/simple-lama-inpainting)

- [问题汇总](https://github.com/shadowcz007/comfyui-mixlab-nodes/issues/294)

> rembgNode

"briarmbg","u2net","u2netp","u2net_human_seg","u2net_cloth_seg","silueta","isnet-general-use","isnet-anime"

**_ briarmbg _** model was developed by BRlA Al and can be used as an open-source model for non-commercial purposes

### Enhancement

- Direct "Help" option accessible through node context menu.

- "Nodes Map" feature added to global context menu.

- An improvement has been made to directly redirect to GitHub to search for missing nodes when loading the graph.

*** If not needed, you can comment out ```app.showMissingNodesError``` in the ```ui_mixlab.js``` file.

![help](./assets/help.png)

![node-not-found](./assets/node-not-found.png)


- Right-click shortcut

右键菜单支持 text-to-text，方便对 prompt 词补全，支持云LLM或者是本地LLM。
The right-click menu supports text-to-text conversion, facilitating prompt word completion, and supports cloud LLMs or local LLMs.

Local LLM API example:```http://localhost:1234/v1```

![alt text](./assets/1724380841822.png)


### Models

- [Download TripoSR](https://huggingface.co/stabilityai/TripoSR/blob/main/model.ckpt) and place it in `models/triposr`

- [Download facebook/dino-vitb16](https://huggingface.co/facebook/dino-vitb16/tree/main) and place it in `models/triposr/facebook/dino-vitb16`

[Download rembg Models](https://github.com/danielgatis/rembg/tree/main#Models),move to:`models/rembg`

[Download lama](https://github.com/enesmsahin/simple-lama-inpainting/releases/download/v0.1.0/big-lama.pt), move to : `models/lama`

[Download Salesforce/blip-image-captioning-base](https://huggingface.co/Salesforce/blip-image-captioning-base), move to :`models/clip_interrogator/Salesforce/blip-image-captioning-base`

[Download succinctly/text2image-prompt-generator](https://huggingface.co/succinctly/text2image-prompt-generator/tree/main),move to:`models/prompt_generator/text2image-prompt-generator`

[Download Helsinki-NLP/opus-mt-zh-en](https://huggingface.co/Helsinki-NLP/opus-mt-zh-en/tree/main),move to:`models/prompt_generator/opus-mt-zh-en`

## Installation

manually install, simply clone the repo into the custom_nodes directory with this command:

```
cd ComfyUI/custom_nodes

git clone https://github.com/shadowcz007/comfyui-mixlab-nodes.git

```

Install the requirements:

run directly:

```
cd ComfyUI/custom_nodes/comfyui-mixlab-nodes
install.bat
```

or install the requirements using:

```
../../../python_embeded/python.exe -s -m pip install -r requirements.txt
```

If you are using a venv, make sure you have it activated before installation and use:

```
pip3 install -r requirements.txt
```

#### Chinese community

访问 [www.mixcomfy.com](https://www.mixcomfy.com)，获得更多内测功能，关注微信公众号：Mixlab 无界社区

####

File / LoadImagesFromPath SaveImageToLocal LoadImagesFromURL

#### discussions:

[discussions](https://github.com/shadowcz007/comfyui-mixlab-nodes/discussions)

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="
      https://star-history.dera.page/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date&theme=dark
    "
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="
      https://star-history.dera.page/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date
    "
  />
  <img
    alt="Star History Chart"
    src="https://star-history.dera.page/svg?repos=shadowcz007/comfyui-mixlab-nodes&type=Date"
  />
</picture>
