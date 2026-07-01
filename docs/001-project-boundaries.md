# 001 — Project Boundaries

## Purpose

This document protects project momentum.

Reality Skin Engine has a large long-term vision, but future capabilities must not become accidental dependencies for the current phase.

## Primary rule

> A future capability is not a dependency for the current phase unless explicitly promoted into scope.

This rule applies to humans, AI agents, contributors, and future planning sessions.

## Current phase

The current phase is the software engine proof.

Scope:

- phone-based AR prototype
- Unity runtime
- AR Foundation
- ARCore first test path
- manual surface labeling
- Reality Pack loading
- 1812 and 3055 visual modes
- demo recording

Out of scope for the current phase:

- custom AR glasses
- custom headset hardware
- EEG
- EMG
- custom wearable hardware
- neural interfaces
- full city-scale reconstruction
- perfect object recognition
- multiplayer
- marketplace
- live AI generation for every frame

## Layer model

### Layer 1 — Reality Skin Engine

Software-first engine.

Goal:

```text
camera
  -> understand surfaces
  -> apply Reality Pack
  -> render alternate interpretation
  -> display on phone
```

This layer must work by itself.

### Layer 2 — Reality Devices

Display and sensor devices.

Examples:

- phone
- tablet
- inexpensive phone headset
- mixed reality headset
- AR glasses
- better cameras
- depth sensors
- custom optics

These improve the experience but do not define the engine.

### Layer 3 — Human Interface System

Advanced input and user-state systems.

Examples:

- voice
- gaze
- gesture
- eye tracking
- rings
- watches
- chest sensors
- EEG
- EMG
- biometrics
- distributed wearable sensor fusion

These belong later. They are important, but they must not block Layer 1.

## Hardware rule

Hardware must not block software unless the software feature explicitly requires that hardware.

If a feature can be approximated with a phone, use the phone first.

## Wearables rule

Wearables are a later phase.

They should be tracked as future architecture, not imported into the phone MVP. They require additional physical materials, sourcing, assembly, testing, body-device ergonomics, and hardware debugging.

The project may reference the future wearable layer, but the engine must not wait for it.

## Glasses rule

AR glasses are a future client, not the first build target.

The phone proves the engine. Glasses improve the display.

## AI agent rule

AI agents may implement defined tasks. They should not silently expand scope.

Before adding a new major layer, an AI agent should check:

1. Is this in the current phase?
2. Does it serve the next demo?
3. Does it require new hardware?
4. Does it create a new dependency?
5. Is it documented in the roadmap?

If the answer is unclear, stop and ask.

## Demo rule

One working demo is more valuable than ten unfinished concepts.

The first demo is:

> Same real place. Same geometry. Switch between neutral, 1812, and 3055.

## Promotion rule

A future layer can be promoted into active scope only when:

- the current layer has a working demo,
- the new layer has a clear purpose,
- required hardware/materials are known,
- cost and setup burden are understood,
- and the roadmap is updated.

## Principle

Keep the full vision visible. Keep the current build narrow enough to finish.
