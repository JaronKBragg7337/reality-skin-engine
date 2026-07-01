# System Architecture

## Architecture summary

Reality Skin Engine is organized around five separable layers:

```text
Reality Capture
  -> Reality Understanding
  -> Reality Interpretation
  -> Reality Rendering
  -> Reality Display
```

The engine should keep these layers distinct so the project can evolve from phone AR to headsets, glasses, and future display systems without rewriting the core logic.

## Layer 1 — Reality Capture

Captures spatial information from the user's environment.

Inputs:

- camera feed
- device pose
- AR tracking
- plane detection
- raycasts
- depth, if available
- scene mesh, later

MVP technologies:

- Unity
- AR Foundation
- ARCore first
- ARKit later

MVP output:

```text
tracked surfaces and anchors
```

## Layer 2 — Reality Understanding

Turns captured geometry into useful meaning.

MVP method:

- manual surface labeling

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
person
```

Later methods:

- assisted AI labels
- local vision models
- depth/mesh classification
- persistent scene memory

MVP output:

```json
{
  "surface_id": "surface-001",
  "label": "wall",
  "anchor_id": "anchor-001",
  "confidence": "manual"
}
```

## Layer 3 — Reality Interpretation

Chooses how a real surface should be visually interpreted.

This layer is driven by Reality Packs.

Example:

```text
label: road
1812 Reality Pack: dirt road
3055 Reality Pack: glowing transit grid
```

Reality Packs are data. The engine should load them without needing code changes.

## Layer 4 — Reality Rendering

Applies the selected interpretation to the live view.

Rendering elements:

- materials
- prefabs
- overlay meshes
- lighting shifts
- fog/atmosphere
- audio
- optional educational labels

MVP rendering should use simple overlays and placeholder materials before complex shaders.

## Layer 5 — Reality Display

Displays the rendered interpretation to the user.

Supported over time:

```text
phone
tablet
phone headset
mixed reality headset
AR glasses
future display client
```

The display is the client, not the engine.

## Runtime structure

Proposed top-level structure:

```text
engine/
  core data models and pack logic

runtime/
  Unity runtime implementation

reality-packs/
  1812, 3055, and future packs

tools/
  pack creation, validation, asset pipeline

demos/
  recorded tests and demo scripts
```

Current repository may still contain early folders such as `assets/era-packs/`. These should migrate toward `reality-packs/` as the architecture stabilizes.

## MVP implementation flow

```text
Unity AR scene
  -> detect plane
  -> user taps plane
  -> user labels plane
  -> store labeled surface
  -> user selects Reality Pack
  -> engine resolves surface rule
  -> runtime applies material/prefab
  -> user records demo
```

## Dependency direction

Higher-level apps may depend on the engine.

The engine should not depend on a single app.

Correct:

```text
App -> Runtime -> Engine -> Reality Pack
```

Avoid:

```text
Engine -> One specific demo app
```

## Architectural rule

Reality Skin Engine is an engine, not an application. Applications are built on top of it.
