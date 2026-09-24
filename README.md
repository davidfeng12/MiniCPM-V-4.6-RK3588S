# MiniCPM-V 4.6 on RK3588S

Deploy **MiniCPM-V 4.6** on Rockchip ** RK3588S** using **RKNN + RKLLM** for fully local multimodal AI inference.

This project focuses on running the MiniCPM-V 4.6 vision-language model on embedded Rockchip platforms, including vision model conversion, RKNN inference, RKLLM deployment, C++ runtime integration, camera input, and performance optimization.

## Features

* MiniCPM-V 4.6 edge deployment
* Rockchip RK3588S support
* RKNN Vision Encoder
* RKLLM language model runtime
* W8A8 LLM quantization
* C++ inference pipeline
* MIPI camera input
* Image-based visual question answering
* Real-time camera inference demo
* Fully offline inference
* NPU acceleration
* Performance optimization examples

## Project Architecture

```text
Camera / Image
      │
      ▼
Image Preprocessing
      │
      ▼
RKNN Vision Encoder
      │
      ▼
Visual Embedding
      │
      ▼
RKLLM Runtime
      │
      ▼
Qwen Language Model
      │
      ▼
Text Response
```

## Hardware

Tested platform:

```text
SoC:        Rockchip RK3588S
NPU:        6 TOPS
OS:         Linux
Camera:     MIPI
Runtime:    RKNN + RKLLM
Language:   C++
```

## Model Components

The deployment pipeline contains two main components.

### Vision Model

```text
MiniCPM-V 4.6 Vision Encoder
        ↓
ONNX Export
        ↓
Graph Optimization
        ↓
RKNN Conversion
        ↓
RK3588S NPU
```

Example model:

```text
minicpm_v46_vision_v3_erf_fp16_rk3588s.rknn
```

### Language Model

```text
MiniCPM-V 4.6
      ↓
Qwen-based LLM
      ↓
RKLLM Toolkit
      ↓
W8A8 Quantization
      ↓
RKLLM Model
```

Example model:

```text
minicpm_v46_qwen35_w8a8_rk3588s.rkllm
```

## Camera Demo

Example command:

```bash
bin/minicpm_v46_camera_demo \
  /dev/video51 \
  models/minicpm_v46_vision_v3_erf_fp16_rk3588s.rknn \
  models/minicpm_v46_qwen35_w8a8_rk3588s.rkllm \
  128 \
  2048 \
  3 \
  rk3588s \
  '<image>' \
  '</image>' \
  '<|image_pad|>'
```

## Example Use Cases

* AI cameras
* Smart outdoor cameras
* Robotics
* Wearable AI devices
* Industrial vision systems
* Smart glasses
* Edge visual assistants
* Offline multimodal assistants
* Embedded computer vision systems



## Roadmap

Future development will focus on:

* Faster camera inference
* Vision model quantization
* Object detection integration
* Bounding box rendering
* On-screen AI labels
* Multi-frame visual understanding
* Video understanding
* Embedded display UI
* Additional RK3588 hardware platforms

## Disclaimer

This is an independent community project focused on deploying MiniCPM-V 4.6 on Rockchip hardware.

It is not officially affiliated with OpenBMB, ModelBest, or Rockchip.

MiniCPM-V, RKNN, RKLLM, and other third-party components remain subject to their respective licenses and terms.

## Commercial Support

Commercial engineering and customization services are available for:

* RK3588S multimodal AI deployment
* RKNN model conversion
* RKLLM model conversion
* Vision encoder optimization
* Edge AI performance optimization
* Camera integration
* Embedded display integration
* Custom VLM deployment
* Embedded AI product development

For commercial cooperation, technical support, custom deployment, or product integration, please contact:

**Email:** [davidfeng@soulsfeng.com](mailto:davidfeng@soulsfeng.com)
**Instagram:** @soulsfeng
**WhatsApp:** +1 (310) 557-6230

## Contact

Project Maintainer: **David Feng**

Email: [davidfeng@soulsfeng.com](mailto:davidfeng@soulsfeng.com)
Instagram: @soulsfeng
WhatsApp: +1 (310) 557-6230

## Contributing

Contributions, bug reports, performance results, and hardware compatibility reports are welcome.

Please open an Issue or Pull Request if you would like to contribute.

## Star the Project

If this project helps your RK3588 multimodal AI deployment, consider giving it a star.

It helps more embedded AI developers discover the project.
