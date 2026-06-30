# 02 — Stack and Materials

## Build stack

### Core development

| Need | Recommended tool | Why |
|---|---|---|
| Native AR prototype | Unity | Mature mobile AR workflow and broad device support |
| AR abstraction layer | AR Foundation | One Unity API over ARKit and ARCore providers |
| iOS AR | ARKit XR Plugin | iPhone/iPad AR support |
| Android AR | ARCore XR Plugin | Android AR support |
| 3D asset creation | Blender | Free, scriptable, strong for props/materials/previs |
| Code assistant | Claude Code / Cursor | Agentic coding, repo edits, debugging |
| Repo | GitHub | Version control, issues, docs, Codex/agent handoff |
| UI/design board | Figma | App screens, pitch diagrams, investor visuals |
| Research notes | Markdown in repo | Keeps decisions auditable |

## Hardware path

### Minimum viable hardware

Use what is available first.

| Item | Priority | Notes |
|---|---:|---|
| iPhone or Android with AR support | Required | Phone MVP comes first |
| Computer that can run Unity | Required | Mac preferred for iOS builds |
| USB cable | Required | Device testing |
| GitHub account | Required | Repo and issue tracking |

### Better hardware

| Item | Priority | Notes |
|---|---:|---|
| iPhone/iPad with LiDAR | High | Better depth and scene reconstruction on supported devices |
| Meta Quest 3 / 3S | Medium | Useful for mixed-reality testing after phone MVP |
| Developer AR glasses | Later | Do not buy first unless there is budget and a clear SDK path |
| Wearables / EEG | Later | Useful for adaptive modes, not required for MVP |

## Software to install

### Required

1. GitHub Desktop or Git CLI.
2. Unity Hub.
3. Unity LTS.
4. Visual Studio Code or Cursor.
5. Blender.
6. Xcode if building to iPhone.
7. Android Studio if building to Android.

### Unity packages

Start with:

```text
com.unity.xr.arfoundation
com.unity.xr.arkit
com.unity.xr.arcore
com.unity.inputsystem
```

Later:

```text
OpenXR Plugin
XR Interaction Toolkit
Addressables
Barracuda / Sentis or other on-device ML path
```

## Asset approach

Do not overbuy assets early. Start with simple primitives and generated textures.

### First asset set

For `1812`:

- Dirt road texture.
- Old brick texture.
- Wood plank texture.
- Lantern or torch prefab.
- Painted sign prefab.

For `3055`:

- Glowing road-grid texture.
- Glass/metal building texture.
- Hologram sign prefab.
- Neon line mesh.
- Drone or light-orb prefab.

## Buy/not-buy list

### Buy only if needed

- Unity Asset Store AR UI templates.
- Low-poly historical props.
- Low-poly sci-fi props.
- Texture/material packs.
- A used LiDAR iPad/iPhone.

### Do not buy first

- Custom AR glasses.
- Expensive motion-capture hardware.
- EEG headset.
- Full 3D city datasets.
- Enterprise AR SDKs.

## Development accounts

Likely needed later:

- Apple Developer account for TestFlight/device distribution.
- Google Play Console for Android testing/distribution.
- Unity account.
- GitHub account.

For the first local prototype, keep distribution private and simple.

## AI agent division of labor

### Claude / GPT / Cursor

Use for:

- Unity C# scripts.
- Repo docs.
- Architecture decisions.
- Debugging build errors.
- Test plans.

### Blender automation

Use for:

- Simple prop generation.
- Material testing.
- Camera previs.
- Exporting FBX/GLB assets.

### Image/video tools

Use for:

- Pitch visuals.
- Style references.
- Texture references.
- Concept art.

## Practical constraint

The early project should be shaped around a single device you can actually test. A working iPhone MVP is more valuable than a theoretical glasses architecture.
