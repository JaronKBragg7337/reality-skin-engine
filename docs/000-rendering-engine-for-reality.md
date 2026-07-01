# 000 — Rendering Engine for Reality

## Core identity

Reality Skin Engine is a rendering engine for reality.

It separates physical geometry from visual interpretation so the same real-world environment can be experienced through different historical, educational, artistic, fictional, accessibility, or future renderings.

## The central split

Reality has at least two layers that should be treated separately:

```text
Physical Geometry
  What is actually there:
  walls, roads, trees, signs, rooms, sidewalks, vehicles, doors, stairs

Visual Interpretation
  How that geometry is rendered:
  1812, 3055, solarpunk, medieval, blueprint, museum, low-stimulation, fantasy
```

Most AR products place isolated virtual objects into the world. Reality Skin Engine treats the world itself as the substrate.

```text
ordinary AR:      add object into reality
Reality Skin:     reinterpret reality itself
```

## Engine, not single app

Reality Skin Engine is not just one AR app.

It is an engine that can support many applications:

- history walks
- museum experiences
- classroom lessons
- city tourism
- real-world games
- film previsualization
- architecture visualization
- accessibility overlays
- calming / low-stimulation modes
- creator-built visual worlds

The first app proves the engine. The engine should not be trapped inside one app concept.

## Displays are clients

The display is not the project. The display is a client of the engine.

```text
Reality Skin Engine
  -> phone
  -> tablet
  -> phone headset
  -> mixed reality headset
  -> AR glasses
  -> future display hardware
```

The first working display is the phone because it is available, cheap, testable, and already has a camera, motion tracking, screen, and development ecosystem.

Glasses are the long-term natural interface, but they are not a dependency for the engine.

## Why phones first

Phones allow the project to prove the hardest product loop immediately:

```text
camera feed
  -> understand real surfaces
  -> label surfaces
  -> apply Reality Pack
  -> render alternate interpretation
  -> user sees changed world
```

If this loop works on a phone, it can later move to headsets and glasses.

If this loop does not work on a phone, custom glasses will not fix the underlying architecture.

## Reality Packs

The engine uses Reality Packs.

A Reality Pack is a data-driven interpretation layer. It defines how real-world labels should be rendered.

Examples:

```text
1812 History Pack
3055 Future Pack
Medieval Pack
Roman Empire Pack
Solarpunk Pack
Cyberpunk Pack
Fantasy Forest Pack
Architectural Blueprint Pack
Low-Stimulation Pack
Museum Guide Pack
```

The older phrase `Era Pack` is now considered a historical subset of `Reality Pack`.

## System spine

```text
Reality Capture
  camera, depth, SLAM, plane detection, mesh

Reality Understanding
  surface labels, object classes, lighting, risk zones

Reality Interpretation
  Reality Packs, rules, mappings, educational notes

Reality Rendering
  materials, props, lighting, atmosphere, audio

Reality Display
  phone, headset, glasses, future clients
```

## Long-term direction

The long-term goal is not to make one novelty AR filter. The goal is to build reusable spatial infrastructure that lets people choose or create alternate interpretations of the real world.

The first proof is simple:

> Same real place. Same geometry. Different rendering.
