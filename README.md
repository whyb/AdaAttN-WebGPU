# AdaAttN风格迁移 Web Demo

这是一个基于静态网页的风格迁移演示项目，利用 [onnxruntime-webgpu](https://github.com/microsoft/onnxruntime) 在浏览器端高效运行 AdaAttN 模型，实现图像风格转换。

## 在线预览

- [项目演示地址](https://whyb.github.io/AdaAttN-WebGPU/)

## 功能说明

- **浏览器端风格迁移**：利用 onnxruntime-webgpu 在浏览器中直接运行 AdaAttN 模型。
- **本地高效推理**：通过 Web Worker 隔离主线程，利用 OpenCV.js 进行图像预处理，确保页面响应流畅。
- **直观操作**：提供简单易用的界面，用户只需上传内容图和风格图，即可在客户端获得风格化后的图像。

## 使用方法

1. **克隆项目**
   将项目克隆到本地：
   ```bash
   git clone https://github.com/whyb/AdaAttN-WebGPU.git

2. **浏览器支持**
    请确保使用支持 WebGPU 和 HTML5 的浏览器：
    - 检查 WebGPU 支持：https://webgpu.io/status/
    - 检查 HTML5 支持：https://html5test.co/

3. **打开页面**
    - 在浏览器中打开项目根目录下的 index.html 文件。

4. **上传图片并推理**
    - 上传用于风格转换的内容图和风格图。
    - 点击“开 始 推 理”按钮开始推理。
    - 等待进度条完成后，风格化后的图像会显示在页面上。

## 内部原理
该项目主要通过以下步骤实现风格迁移：

* 图像预处理：使用 OpenCV.js 进行图像尺寸调整和数据格式转换；
* 数据转换：将预处理后的图像数据转换为符合 ONNX 模型输入要求的 Tensor；
* 模型推理：利用 onnxruntime-webgpu 实现 AdaAttN 模型的高效推理；
* 结果展示：将模型输出的风格化图像数据在 HTML Canvas 上渲染显示。

所有的计算都在一个 Web Worker 中进行，以避免阻塞主线程，确保用户界面流畅。

## 项目引用链接

- GitHub 项目地址：[AdaAttN-WebGPU](https://github.com/whyb/AdaAttN-WebGPU)
- AdaAttN ONNX 模型：[AdaAttN-onnx](https://github.com/whyb/AdaAttN-onnx)
- AdaAttN PyTorch 模型：[AdaAttN](https://github.com/Huage001/AdaAttN/)
