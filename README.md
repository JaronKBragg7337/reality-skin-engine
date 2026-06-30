# Reality Skin Engine

Reality Skin Engine is an AR/spatial-computing project that reskins the visible world into different eras, futures, moods, or fictional interpretations while preserving the user's live physical environment.

The core principle:

> Do not replace reality. Re-render the user's perception of reality.

A phone, headset, or future glasses sees the environment, detects surfaces and objects, anchors geometry, then applies an era/style pack: 1812, 1500s, 3055, solarpunk, medieval, Roman, alien-world, museum mode, or creator-built worlds.

## MVP target

The first version is not custom glasses. The first version is a phone-based AR prototype.

The MVP should let a user:

1. Open the app on an AR-capable phone.
2. Detect planes and basic surfaces.
3. Manually label surfaces such as road, wall, sign, object, tree, or vehicle.
4. Apply an era pack such as `1812` or `3055`.
5. See the same physical space rendered with different textures, props, lighting, and overlays.
6. Record a demo video that proves the concept.

## Repository map

```text
reality-skin-engine/
  README.md
  docs/
    00-vision.md
    01-mvp-blueprint.md
    02-stack-and-materials.md
    03-era-pack-format.md
    04-roadmap.md
    05-privacy-safety.md
  assets/
    era-packs/
      1812/
      3055/
  app/
    unity-prototype/
    webar-prototype/
  research/
    ar-sdk-notes.md
    scene-understanding.md
    ai-generation-pipeline.md
```

## Build philosophy

This project should be built capability-mapping first:

- Observe what ARKit/ARCore/Unity can actually do on available hardware.
- Build the smallest proof that demonstrates the world-reskin loop.
- Do not over-constrain the system before observing real failure modes.
- Avoid jumping directly to custom hardware, EEG control, or city-scale reconstruction.
- Treat creator packs, education packs, tourism packs, and cinematic packs as downstream layers.

## Primary build track

Use Unity + AR Foundation for the first native prototype.

Why:

- It can target iOS and Android.
- It supports plane detection, raycasts, anchors, AR camera, and tracked poses through platform providers.
- It keeps the door open for XR hardware later.
- It is widely understood by AR developers and AI coding agents.

## First demo definition

A successful first demo is:

> Stand in one real place, point the phone at it, tap `1812`, and see the road/wall/sign space visually converted into an older-era scene. Tap `3055`, and the same geometry becomes a future-city skin.

The first demo does not need perfect object recognition. Manual tagging is allowed.

## Immediate next steps

1. Install Unity Hub and a current LTS Unity version.
2. Create a Unity project under `app/unity-prototype/`.
3. Add AR Foundation plus ARKit XR Plugin for iOS and/or ARCore XR Plugin for Android.
4. Build a plane-detection scene.
5. Add the first era-pack loader using the JSON format in `docs/03-era-pack-format.md`.
6. Record the first pitch demo.
