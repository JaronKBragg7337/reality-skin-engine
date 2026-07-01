# Reality Skin Engine

> **A rendering engine for reality.**

Reality Skin Engine separates physical geometry from visual interpretation so the same real-world environment can be experienced through different historical, educational, artistic, fictional, accessibility, or future renderings.

The core principle:

> Do not replace reality. Re-render the user's perception of reality.

A phone, headset, or future glasses sees the environment, detects surfaces and objects, anchors geometry, then applies a **Reality Pack**: 1812, 1500s, 3055, solarpunk, medieval, Roman, alien-world, museum mode, blueprint mode, low-stimulation mode, or creator-built worlds.

## Engine, not single app

Reality Skin Engine is an engine, not an application. Applications are built on top of it.

```text
Reality Capture
  -> Reality Understanding
  -> Reality Interpretation
  -> Reality Rendering
  -> Reality Display
```

The display is a client:

```text
phone
  -> phone headset
  -> mixed reality headset
  -> AR glasses
  -> future display hardware
```

## MVP target

The first version is not custom glasses. The first version is a phone-based AR prototype.

The MVP should let a user:

1. Open the app on an AR-capable phone.
2. Detect planes and basic surfaces.
3. Manually label surfaces such as road, wall, sign, object, tree, or vehicle.
4. Apply a Reality Pack such as `1812` or `3055`.
5. See the same physical space rendered with different textures, props, lighting, and overlays.
6. Record a demo video that proves the concept.

## Repository map

```text
reality-skin-engine/
  README.md
  AGENTS.md
  CONTRIBUTING.md
  DECISIONS.md
  DESIGN_PRINCIPLES.md
  SYSTEM_ARCHITECTURE.md
  TERMINOLOGY.md
  docs/
    000-rendering-engine-for-reality.md
    001-project-boundaries.md
    00-vision.md
    01-mvp-blueprint.md
    02-stack-and-materials.md
    03-era-pack-format.md
    04-roadmap.md
    05-privacy-safety.md
    06-machine-capabilities.md
  engine/
  runtime/
  reality-packs/
    1812/
    3055/
  tools/
  demos/
  research/
```

Early legacy folders may still exist under `assets/era-packs/`. New work should prefer `reality-packs/` and the term **Reality Pack**.

## Build philosophy

This project should be built capability-mapping first:

- Observe what ARCore/ARKit/Unity can actually do on available hardware.
- Build the smallest proof that demonstrates the world-reskin loop.
- Do not over-constrain the system before observing real failure modes.
- Avoid jumping directly to custom hardware, EEG control, or city-scale reconstruction.
- Treat creator packs, education packs, tourism packs, cinematic packs, wearables, and glasses as downstream layers.

## Primary build track

Use Unity + AR Foundation for the first native prototype.

Current practical path:

```text
Windows build station
  -> Unity + AR Foundation
  -> Android Build Support
  -> ARCore test on Android device
  -> iOS later through Mac/Xcode or Unity Build Automation
```

Why:

- Android testing is available immediately after installing the Unity Android module.
- The current build station is Windows.
- iPhone support remains valuable, but local signed iOS builds require macOS/Xcode or a cloud build path.
- Unity can target both Android and iOS through provider plugins.
- The engine concept stays broader than any one runtime.

## First demo definition

A successful first demo is:

> Stand in one real place, point the phone at it, tap `1812`, and see the road/wall/sign space visually converted into an older-era scene. Tap `3055`, and the same geometry becomes a future-city skin.

The first demo does not need perfect object recognition. Manual tagging is allowed.

## Immediate next steps

1. Install Unity Android Build Support, SDK/NDK Tools, and OpenJDK.
2. Create a Unity project under `runtime/unity-prototype/`.
3. Add AR Foundation and ARCore XR Plugin.
4. Build a plane-detection scene.
5. Add manual surface labels.
6. Add a Reality Pack loader using the JSON format in `docs/03-era-pack-format.md`.
7. Apply the `1812` and `3055` packs from `reality-packs/`.
8. Record the first pitch demo.
