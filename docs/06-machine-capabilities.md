# 06 — Machine Capabilities

## Current build station

This machine is strong enough to serve as the main build/prototype station for Reality Skin Engine.

## Hardware

```text
CPU: Intel Core i9-14900HX, 24 cores / 32 threads
GPU: NVIDIA GeForce RTX 4060 Laptop GPU
VRAM: 8 GB
RAM: 32 GB
Storage: C: 928.6 GB total / 559.3 GB free; G: 300 GB total / 171.2 GB free
OS: Windows 11 Home 64-bit, build 26200
```

## Core development tools

```text
Unity version: 6000.4.11f1, Unity Hub 3.18.2
Unity modules installed: Windows Standalone, WebGL
Unity modules missing: iOS Build Support, Android Build Support
Unreal version: UE 5.6 and UE 5.8
Blender version: 5.1.2
Docker: installed, daemon not currently running
GitHub CLI: 2.93.0
Codex CLI: 0.141.0
Claude Code: 2.1.181
```

## AI / GPU stack

```text
NVIDIA driver: 595.79
CUDA installed: yes, driver reports CUDA 13.2; nvcc toolkit is CUDA 13.3.33
Ollama: 0.30.10
Local AI models: llama3.2:3b and qwen3.5:4b
```

## 3D and art tools

```text
Blender
Maya 2026
Substance 3D Painter
Inkscape
Krita
OBS
FFmpeg
```

## Dev tools

```text
VS Code
Visual Studio Build Tools 2022
Windows SDK
Python
Node
.NET
Java
CMake
uv
```

## Capability assessment

### Strong fits

- Unity scene creation.
- AR Foundation project setup.
- Android AR build path once Android Build Support is installed.
- Blender/Maya/Substance asset pipeline.
- Local AI experiments using Ollama.
- GPU-assisted generation/vision experiments within 8 GB VRAM limits.
- GitHub/Codex/Claude repo-based development.
- OBS/FFmpeg demo capture.

### Current blockers

- Direct iPhone builds are not ready from this Windows machine.
- Unity iOS Build Support is missing.
- Local Xcode builds require macOS.
- Android Build Support is also missing.
- Docker daemon is installed but not currently running.

## Immediate build strategy

Use this PC for:

1. Unity project setup.
2. AR Foundation scene creation.
3. Blender/Maya/Substance asset creation.
4. Era-pack authoring.
5. Local AI/Ollama experiments.
6. GitHub/Codex/Claude task execution.

Use Lillith's Android device for early AR testing after installing Android Build Support.

Use one of these paths for iPhone testing:

1. A Mac with Xcode.
2. Unity Build Automation/cloud build.
3. Install iOS Build Support for project export, then complete signing/building through macOS/Xcode.

## Recommended immediate action

Because Android testing is available through Lillith's device, the fastest path is:

```text
Install Android Build Support
→ install ARCore XR Plugin
→ build to Android first
→ keep iPhone as second target through Mac/cloud build
```

This avoids blocking the MVP on Apple's build chain.
