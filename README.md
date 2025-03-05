<!-- Ultralytics 🚀 AGPL-3.0 License - https://ultralytics.com/license -->

<div align="center">
  <p>
    <a href="https://www.ultralytics.com/yolo/yolo27?utm_source=github&utm_medium=social&utm_campaign=yolo27-launch-2026&utm_content=banner" target="_blank">
      <img width="100%" src="https://raw.githubusercontent.com/ultralytics/assets/main/yolov8/banner-yolov8.png" alt="Ultralytics YOLO banner"></a>
  </p>

[中文](https://docs.ultralytics.com/zh/inference) | [한국어](https://docs.ultralytics.com/ko/inference) | [日本語](https://docs.ultralytics.com/ja/inference) | [Русский](https://docs.ultralytics.com/ru/inference) | [Deutsch](https://docs.ultralytics.com/de/inference) | [Français](https://docs.ultralytics.com/fr/inference) | [Español](https://docs.ultralytics.com/es/inference) | [Português](https://docs.ultralytics.com/pt/inference) | [Türkçe](https://docs.ultralytics.com/tr/inference) | [Tiếng Việt](https://docs.ultralytics.com/vi/inference) | [العربية](https://docs.ultralytics.com/ar/inference) <br>

</div>

# 🦀 Ultralytics YOLO Rust Inference

<div align="center">

[English](README.md) | [简体中文](README.zh-CN.md)

</div>

<div align="center">

[![Ultralytics Discord](https://img.shields.io/discord/1089800235347353640?logo=discord&logoColor=white&label=Discord&color=blue)](https://discord.com/invite/ultralytics)
[![Ultralytics Forums](https://img.shields.io/discourse/users?server=https%3A%2F%2Fcommunity.ultralytics.com&logo=discourse&label=Forums&color=blue)](https://community.ultralytics.com)
[![Ultralytics Reddit](https://img.shields.io/reddit/subreddit-subscribers/ultralytics?style=flat&logo=reddit&logoColor=white&label=Reddit&color=blue)](https://www.reddit.com/r/Ultralytics/)
[![codecov](https://codecov.io/github/ultralytics/inference/branch/main/graph/badge.svg)](https://app.codecov.io/github/ultralytics/inference)
[![CI](https://github.com/ultralytics/inference/actions/workflows/ci.yml/badge.svg)](https://github.com/ultralytics/inference/actions/workflows/ci.yml)
[![arXiv](https://img.shields.io/badge/arXiv-2606.03748-b31b1b?logo=arxiv&logoColor=white)](https://arxiv.org/abs/2606.03748)

[![Crates.io](https://img.shields.io/crates/v/ultralytics-inference?logo=rust&logoColor=white&label=crates.io&color=CE422B)](https://crates.io/crates/ultralytics-inference)
[![docs.rs](https://img.shields.io/docsrs/ultralytics-inference?logo=docs.rs&logoColor=white&label=docs.rs&color=CE422B)](https://docs.rs/ultralytics-inference)
[![Downloads](https://img.shields.io/crates/d/ultralytics-inference?logo=rust&logoColor=white&label=downloads&color=CE422B)](https://crates.io/crates/ultralytics-inference)
[![MSRV](https://img.shields.io/crates/msrv/ultralytics-inference?logo=rust&logoColor=white&color=CE422B)](https://crates.io/crates/ultralytics-inference)
[![License](https://img.shields.io/crates/l/ultralytics-inference?label=license&color=blue)](https://github.com/ultralytics/inference/blob/main/LICENSE)
[![dependency status](https://deps.rs/repo/github/ultralytics/inference/status.svg)](https://deps.rs/repo/github/ultralytics/inference)

</div>

[Ultralytics](https://www.ultralytics.com) creates cutting-edge, state-of-the-art (SOTA) [YOLO models](https://www.ultralytics.com/yolo) built on years of foundational research in computer vision and AI. Constantly updated for performance and flexibility, our models are **fast**, **accurate**, and **easy to use**. They excel at [object detection](https://docs.ultralytics.com/tasks/detect), [instance segmentation](https://docs.ultralytics.com/tasks/segment), [semantic segmentation](https://docs.ultralytics.com/tasks/semantic), [depth estimation](https://docs.ultralytics.com/tasks/depth), [image classification](https://docs.ultralytics.com/tasks/classify), [pose estimation](https://docs.ultralytics.com/tasks/pose), and [oriented bounding box](https://docs.ultralytics.com/tasks/obb) tasks.

This is a high-performance YOLO inference library written in Rust, giving those models a fast, safe, and efficient interface on [ONNX Runtime](https://onnxruntime.ai). It runs every task above over images, video files, and webcam or RTSP streams, with an API designed to match the [Ultralytics Python package](https://github.com/ultralytics/ultralytics) and no Python or PyTorch runtime required.

Find detailed documentation in the [Ultralytics Docs](https://docs.ultralytics.com/inference). Get support via [GitHub Issues](https://github.com/ultralytics/inference/issues/new/choose). Join discussions on [Discord](https://discord.com/invite/ultralytics), [Reddit](https://www.reddit.com/r/ultralytics/), and the [Ultralytics Community Forums](https://community.ultralytics.com)!

Request an Enterprise License for commercial use at [Ultralytics Licensing](https://www.ultralytics.com/license).

## ✨ Features

- 🚀 **High Performance** - Pure Rust implementation with zero-cost abstractions
- 🎯 **Ultralytics API Compatible** - `Results`, `Boxes`, `Masks`, `Keypoints`, `Probs`, `Obb`, `SemanticMask`, and `DepthMap` types matching the Python API shape
- 🔧 **Multiple Backends** - CPU, XNNPACK, CUDA, TensorRT, CoreML, OpenVINO, and more via ONNX Runtime
- 📦 **Dual Use** - Library for Rust projects + standalone CLI application
- 🏷️ **Auto Metadata** - Automatically reads class names, task type, and input size from ONNX models
- ⬇️ **Auto Download** - Downloads supported YOLO26, YOLO11, and YOLOv8 ONNX models (sizes: n/s/m/l/x) when not found locally
- 🖼️ **Multiple Sources** - Images, directories, glob patterns, video files, webcams, and streams
- 🪶 **Lean Runtime** - No PyTorch, TensorFlow, or Python runtime required

## ✨ Models

<a href="https://docs.ultralytics.com/tasks" target="_blank">
    <img width="100%" src="https://cdn.ul.run/i/c99d914c3958d0755b5a3d7204b6f24a.avif" alt="Ultralytics YOLO supported tasks">
</a>
<br>
<br>

This crate runs [YOLOv8](https://docs.ultralytics.com/models/yolov8), [YOLO11](https://docs.ultralytics.com/models/yolo11), and [YOLO26](https://docs.ultralytics.com/models/yolo26) ONNX models. They cover [Detection](https://docs.ultralytics.com/tasks/detect), [Segmentation](https://docs.ultralytics.com/tasks/segment), [Semantic Segmentation](https://docs.ultralytics.com/tasks/semantic), monocular [Depth Estimation](https://docs.ultralytics.com/tasks/depth) (YOLO26 only), [Classification](https://docs.ultralytics.com/tasks/classify), [Pose Estimation](https://docs.ultralytics.com/tasks/pose), and [OBB](https://docs.ultralytics.com/tasks/obb), pretrained on [COCO](https://docs.ultralytics.com/datasets/detect/coco) for detection, segmentation, and pose, on [Cityscapes](https://docs.ultralytics.com/datasets/semantic/cityscapes) for semantic segmentation, on [ImageNet](https://docs.ultralytics.com/datasets/classify/imagenet) for classification, and on [DOTA](https://docs.ultralytics.com/datasets/obb/dota-v2) for OBB. All [models](https://docs.ultralytics.com/models) download automatically from the latest Ultralytics [release](https://github.com/ultralytics/assets/releases) on first use.

[RT-DETR](https://docs.ultralytics.com/models/rtdetr) detection models also run. There is no prebuilt RT-DETR ONNX to download, so export one yourself first (see below). After that it loads and runs like any other model here, on every device this crate supports.

## 🚀 Quick Start

### Prerequisites

- [Rust 1.92+](https://rustup.rs/) (install via rustup)
- A YOLO ONNX model (export from Ultralytics: `yolo export model=yolo26n.pt format=onnx`)

### System dependencies

Building from source (this includes `cargo install`) compiles native crates, so you need a C compiler. On Linux you additionally need `pkg-config` and the OpenSSL development headers, which the HTTPS model/asset downloader links against. macOS and Windows use their system TLS backends, so a C toolchain is all that is required.

```bash
# Debian/Ubuntu
sudo apt install build-essential pkg-config libssl-dev

# Fedora/RHEL
sudo dnf install gcc gcc-c++ pkgconf-pkg-config openssl-devel

# Arch
sudo pacman -S base-devel openssl pkgconf

# macOS (Xcode Command Line Tools provide the clang compiler)
xcode-select --install

# Windows: install the "Desktop development with C++" workload from
# Visual Studio Build Tools (https://visualstudio.microsoft.com/downloads/)
```

### Installation

```bash
# Install CLI globally from crates.io
cargo install ultralytics-inference

# Install CLI globally with custom features
# Minimal build (no default features)
cargo install ultralytics-inference --no-default-features

# Enable video support
cargo install ultralytics-inference --features video

# Enable multiple accelerators
cargo install ultralytics-inference --features "cuda,tensorrt"
```

### Development install

```bash
# Install CLI directly from the git repository
cargo install --git https://github.com/ultralytics/inference.git ultralytics-inference

# Or clone, build, and install from source
git clone https://github.com/ultralytics/inference.git
cd inference
cargo build --release

# Install from local checkout
cargo install --path . --locked
```

`cargo install` places binaries in Cargo's default bin directory:

- macOS/Linux: `~/.cargo/bin`
- Windows: `%USERPROFILE%\.cargo\bin`

Ensure this directory is in your `PATH`, then run from anywhere:

```bash
ultralytics-inference help
```

### Export a YOLO Model to ONNX

These examples use Ultralytics `>=8.4.142`. For detect, segment, pose, and OBB,
`nms=None` (the default) exports raw one-to-many outputs and this library runs NMS;
`nms=False` selects the NMS-free one-to-one head when available (e.g. YOLO26);
`nms=True` embeds NMS in the ONNX graph. All three output layouts are supported.
Use `nms=None` for semantic, depth, and classify. Existing compatible ONNX files
continue to load without re-exporting.

```bash
pip install -U "ultralytics[export-base]>=8.4.142"

# Using Ultralytics CLI (FP32, default)
yolo export model=yolo26n.pt format=onnx

# FP16 - ~50% smaller model
yolo export model=yolo26n.pt format=onnx quantize=16

# RT-DETR (detection only)
yolo export model=rtdetr-l.pt format=onnx
```

```python
# Or with Python
from ultralytics import YOLO

model = YOLO("yolo26n.pt")
model.export(format="onnx")  # FP32 (default)
model.export(format="onnx", quantize=16)  # FP16
```

```python
# RT-DETR uses its own class
from ultralytics import RTDETR

RTDETR("rtdetr-l.pt").export(format="onnx")
```

> **Precision / quantization:** Ultralytics ≥8.4 uses a single `quantize`
> argument instead of the deprecated `half=True` / `int8=True` flags. For ONNX
> the supported values are `32`/`fp32` (FP32, the default), `16`/`fp16` (FP16),
> and `8`/`int8` (INT8, requires a calibration dataset via `data=`). The old
> flags still work but emit a deprecation warning. See the
> [export docs](https://docs.ultralytics.com/modes/export) and the
> [ONNX integration guide](https://docs.ultralytics.com/integrations/onnx).

### Run Inference

```bash
# With defaults (auto-downloads yolo26n.onnx and sample images)
ultralytics-inference predict

# Select task: auto-downloads the nano model for that task
ultralytics-inference predict --task segment  # downloads yolo26n-seg.onnx
ultralytics-inference predict --task semantic # downloads yolo26n-sem.onnx (YOLO26 only)
ultralytics-inference predict --task depth    # downloads yolo26n-depth.onnx (YOLO26 only)
ultralytics-inference predict --task classify # downloads yolo26n-cls.onnx
ultralytics-inference predict --task pose     # downloads yolo26n-pose.onnx
ultralytics-inference predict --task obb      # downloads yolo26n-obb.onnx

# With explicit model (task is read from model metadata)
ultralytics-inference predict --model yolo26n.onnx --source image.jpg

# Auto-download any supported size (n/s/m/l/x) across YOLO26, YOLO11, and YOLOv8
ultralytics-inference predict --model yolo26l.onnx --source image.jpg
ultralytics-inference predict --model yolo11x-seg.onnx --source image.jpg
ultralytics-inference predict --model yolov8n.onnx --source image.jpg

# RT-DETR, using the ONNX file you exported above
ultralytics-inference predict --model rtdetr-l.onnx --source image.jpg

# On a directory of images
ultralytics-inference predict --model yolo26n.onnx --source assets/

# With custom thresholds
ultralytics-inference predict -m yolo26n.onnx -s image.jpg --conf 0.5 --iou 0.45

# Filter by class IDs
ultralytics-inference predict --model yolo26n.onnx --source image.jpg --classes 0
ultralytics-inference predict --model yolo26n.onnx --source image.jpg --classes "0,1,2"

# With visualization and custom image size
ultralytics-inference predict --model yolo26n.onnx --source video.mp4 --show --imgsz 1280

# Save individual frames for video input
ultralytics-inference predict --model yolo26n.onnx --source video.mp4 --save-frames

# Rectangular inference
ultralytics-inference predict --model yolo26n.onnx --source image.jpg --rect

# Semantic segmentation: write per-image PNG class maps to runs/semantic/predictN/results/
ultralytics-inference predict --task semantic --source cityscapes/ --save-json

# Depth estimation: blend the colorized depth over the image into runs/depth/predictN/
ultralytics-inference predict --task depth --source image.jpg
```

### Example Output

```bash
ultralytics-inference predict
```

```text
WARNING ⚠️ 'model' argument is missing. Using default '--model=yolo26n.onnx'.
WARNING ⚠️ 'source' argument is missing. Using default images: https://ultralytics.com/images/bus.jpg, https://ultralytics.com/images/zidane.jpg
Ultralytics Inference 0.0.50 🚀 Rust ONNX FP32 CPU
Using ONNX Runtime CPUExecutionProvider
YOLO26n summary: 80 classes, imgsz=(640, 640)

image 1/2 /home/ultralytics/inference/bus.jpg: 640x480 4 persons, 1 bus, 36.4ms
image 2/2 /home/ultralytics/inference/zidane.jpg: 384x640 2 persons, 1 tie, 28.6ms
Speed: 1.5ms preprocess, 32.5ms inference, 0.5ms postprocess per image at shape (1, 3, 384, 640)
Results saved to runs/detect/predict
💡 Learn more at https://docs.ultralytics.com/modes/predict
```

**With `--task` (auto-downloads the matching nano model):**

```bash
ultralytics-inference predict --task segment
```

```text
WARNING ⚠️ 'model' argument is missing. Using default '--model=yolo26n-seg.onnx'.
WARNING ⚠️ 'source' argument is missing. Using default images: https://ultralytics.com/images/bus.jpg, https://ultralytics.com/images/zidane.jpg
Ultralytics Inference 0.0.50 🚀 Rust ONNX FP32 CPU
Using ONNX Runtime CPUExecutionProvider
YOLO26n-seg summary: 80 classes, imgsz=(640, 640)

image 1/2 /home/ultralytics/inference/bus.jpg: 640x480 4 persons, 1 bus, 48.2ms
image 2/2 /home/ultralytics/inference/zidane.jpg: 384x640 2 persons, 1 tie, 38.1ms
Speed: 1.6ms preprocess, 44.3ms inference, 1.2ms postprocess per image at shape (1, 3, 384, 640)
Results saved to runs/segment/predict
💡 Learn more at https://docs.ultralytics.com/modes/predict
```

## 📚 Usage

### As a CLI Tool

```bash
# Show help
ultralytics-inference help

# Show version
ultralytics-inference version

# Run inference
ultralytics-inference predict --model yolo26n.onnx --source image.jpg
```

`--help` and `--version` are also supported as standard flag aliases.

**CLI Options:**

| Option               | Short | Description                                                                                                                                                                                                       | Default                                                                      |
| -------------------- | ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `--model`            | `-m`  | Path to ONNX model file; auto-downloaded if a known YOLOv8/YOLO11/YOLO26 name                                                                                                                                     | `yolo26n.onnx`                                                               |
| `--task`             |       | Task type (`detect`, `segment`, `semantic`\*, `depth`\*, `classify`, `pose`, `obb`); selects nano model when `--model` is omitted                                                                                 | `detect`                                                                     |
| `--source`           | `-s`  | Input source (image, directory, glob, video, webcam index, or URL)                                                                                                                                                | Task-dependent Ultralytics URL assets                                        |
| `--conf`             |       | Confidence threshold                                                                                                                                                                                              | `0.25`                                                                       |
| `--iou`              |       | IoU threshold for NMS                                                                                                                                                                                             | `0.7`                                                                        |
| `--max-det`          |       | Maximum number of detections                                                                                                                                                                                      | `300`                                                                        |
| `--imgsz`            |       | Inference image size                                                                                                                                                                                              | model metadata                                                               |
| `--rect [<BOOL>]`    |       | Enable rectangular inference (minimal padding)                                                                                                                                                                    | `true`                                                                       |
| `--batch`            |       | Batch size for inference                                                                                                                                                                                          | `1`                                                                          |
| `--quantize`         |       | Inference precision: `8`, `16`, `32`, `int8`, `fp16`, `fp32`, `w8a8`, `w16a16`, `w32a32`, `w8a16`, or `w8a32`                                                                                                     | Model precision                                                              |
| `--save [<BOOL>]`    |       | Save annotated results to runs/\<task\>/predict                                                                                                                                                                   | `true`                                                                       |
| `--save-frames`      |       | Save individual frames for video input (instead of video file)                                                                                                                                                    | `false`                                                                      |
| `--save-json`        |       | Save semantic segmentation class-map PNGs for external evaluation                                                                                                                                                 | `false`                                                          