# Terminology

## Reality Skin Engine

A rendering engine for reality that separates physical geometry from visual interpretation.

## Rendering engine for reality

The governing concept for the project. The engine uses live spatial understanding to render alternate interpretations of the real world.

## Physical geometry

The actual structure of the world:

- roads
- floors
- walls
- buildings
- doors
- signs
- vehicles
- trees
- people
- stairs
- objects

## Visual interpretation

The rendered meaning or appearance applied to physical geometry.

Examples:

- 1812 street
- 3055 city
- medieval village
- solarpunk district
- blueprint mode
- museum mode
- low-stimulation mode

## Reality Pack

A data-driven package that defines how physical geometry should be visually interpreted.

A Reality Pack can include:

- materials
- prefabs
- surface rules
- lighting rules
- atmosphere rules
- audio
- educational notes
- safety constraints

## Era Pack

Legacy/subcategory term for historical or time-period Reality Packs.

Use `Reality Pack` for new docs and code unless specifically discussing historical packs.

## Reality Capture

The layer that gathers spatial data from the real environment.

Examples:

- camera
- pose tracking
- plane detection
- depth
- mesh reconstruction
- raycasts
- anchors

## Reality Understanding

The layer that turns captured geometry into meaning.

Examples:

- surface label: road
- surface label: wall
- object class: vehicle
- protected class: person
- risk class: stairs

## Reality Interpretation

The layer that decides how a label or object should be rendered under the active Reality Pack.

Example:

```text
wall + 1812 -> old brick
wall + 3055 -> glass/carbon panel
```

## Reality Rendering

The layer that applies visual/audio output to the user's live view.

Examples:

- overlay material
- replacement prefab
- fog
- lighting shift
- hologram sign
- ambient audio

## Reality Display

The client device that shows the rendered result.

Examples:

- phone
- tablet
- phone headset
- mixed reality headset
- AR glasses

## Surface

A detected or user-defined piece of geometry that can receive labels or rendering rules.

## Surface label

A semantic tag assigned to a surface.

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

## Anchor

A tracked position/orientation in AR space used to keep content attached to a real-world location.

## Runtime

An implementation layer that runs the engine on a specific platform or framework.

Example:

- Unity runtime
- Unreal runtime
- native mobile runtime
- future glasses runtime

## App

A user-facing application built on top of the engine.

The app is not the same as the engine.

## Demo

A recorded or live proof of capability.

First demo:

> Same real place. Same geometry. Switch between neutral, 1812, and 3055.
