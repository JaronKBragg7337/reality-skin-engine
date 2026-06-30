# 01 — MVP Blueprint

## MVP objective

Build a phone-based AR prototype that lets a user point at a real environment, label surfaces, and switch between at least two era skins.

The first target is not perfect AR. The first target is a fundable proof:

> Same real place. Same geometry. Different era rendering.

## MVP experience

User flow:

1. Open app.
2. Camera feed starts.
3. AR session detects planes.
4. User taps a surface.
5. User labels it: road, wall, sign, ground, tree, object, vehicle.
6. User selects an era: `1812` or `3055`.
7. App applies a visual skin to the labeled surface.
8. User records the result.

## Technical architecture

```text
Unity App
  ├── AR Session
  ├── AR Camera
  ├── Plane Detection
  ├── Raycast Tap Input
  ├── Manual Surface Labeler
  ├── Era Pack Loader
  ├── Overlay Material System
  ├── Prop Spawner
  └── Demo Recorder / Screen Recording
```

## MVP feature list

### Required

- Native mobile AR scene.
- Plane detection.
- Tap-to-place overlay.
- Manual surface labels.
- Era selector UI.
- Material swapping.
- Simple prop spawning.
- At least two era packs.
- Testable on one real device.

### Optional but valuable

- Depth-based occlusion.
- Scene mesh where supported.
- Basic object detection.
- Persistent anchors.
- Voice command era switching.
- Capture button or instructions for screen recording.

## First prototype scene

Create a Unity scene named:

```text
RealitySkinMVP.unity
```

Required objects:

```text
AR Session
XR Origin / AR Session Origin
AR Camera
AR Plane Manager
AR Raycast Manager
EraSkinManager
SurfaceLabelManager
EraPackLoader
SimpleUI
```

## Manual labeling system

Manual labeling is intentional. It avoids blocking the MVP on AI recognition.

Initial labels:

```text
road
ground
wall
building
sign
tree
vehicle
object
sky
water
```

When the user taps a detected plane or spawned proxy mesh, the app stores:

```json
{
  "anchor_id": "generated-id",
  "label": "wall",
  "position": [0, 0, 0],
  "rotation": [0, 0, 0, 1],
  "scale": [1, 1, 1]
}
```

## Era skin behavior

Each era pack maps a real-world label to a visual interpretation.

Example:

```text
label: road
1812: dirt road material
3055: glowing transit-grid material
```

```text
label: sign
1812: wooden sign prefab
3055: hologram sign prefab
```

## First demo requirements

Record three short clips:

### Clip A — Neutral

Show the real scene with detected surfaces.

### Clip B — 1812

Apply older-world materials and props.

### Clip C — 3055

Apply future-world materials and props.

## Definition of done

The MVP is complete when:

- The app runs on a phone.
- At least one surface can be labeled.
- At least two era modes can be toggled.
- Each mode visibly changes the real environment.
- A demo video can be recorded without explaining the architecture.

## Build sequence

### Day 1 — Setup

- Install Unity Hub.
- Install Unity LTS.
- Install iOS Build Support and/or Android Build Support.
- Create Unity project.
- Add AR Foundation.
- Add ARKit XR Plugin for iOS and/or ARCore XR Plugin for Android.

### Day 2 — AR scene

- Add AR Session.
- Add XR Origin.
- Add AR Plane Manager.
- Add AR Raycast Manager.
- Confirm plane detection on device.

### Day 3 — Manual overlay

- Tap plane.
- Place quad or mesh overlay.
- Apply test material.
- Add simple UI buttons.

### Day 4 — Era pack JSON

- Create JSON loader.
- Load 1812 pack.
- Load 3055 pack.
- Map labels to materials/prefabs.

### Day 5 — Demo polish

- Add 2–3 materials per era.
- Add 1–2 simple props per era.
- Record demo.
- Write notes on limitations.

## Key rule

Do not wait for perfect glasses, perfect object detection, or perfect historical accuracy. Prove the loop first.
