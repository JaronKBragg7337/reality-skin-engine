# AGENTS.md

## Purpose

This file defines how AI coding agents should work in this repository.

The project is Reality Skin Engine: a rendering engine for reality. Do not reduce it to a novelty AR filter or a single Unity demo.

## Primary identity

> Reality Skin Engine is an engine, not an application. Applications are built on top of it.

## Current active scope

Current phase:

- phone-based AR MVP
- Unity runtime
- AR Foundation
- ARCore-first testing path
- manual surface labeling
- Reality Pack loading
- 1812 and 3055 modes

Out of scope unless explicitly promoted:

- EEG
- custom wearables
- custom AR glasses
- neural interfaces
- multiplayer
- marketplace
- full city-scale reconstruction
- live AI generation for every frame

## Required reading before major changes

Before changing architecture, read:

1. `docs/000-rendering-engine-for-reality.md`
2. `docs/001-project-boundaries.md`
3. `SYSTEM_ARCHITECTURE.md`
4. `DESIGN_PRINCIPLES.md`
5. `TERMINOLOGY.md`
6. `DECISIONS.md`

## Naming rules

Use current terms:

- Reality Skin Engine
- Reality Pack
- Reality Capture
- Reality Understanding
- Reality Interpretation
- Reality Rendering
- Reality Display

Avoid introducing conflicting terms unless you update `TERMINOLOGY.md` and explain the decision in `DECISIONS.md`.

`Era Pack` is a legacy/subcategory term. Use `Reality Pack` for new docs and code.

## Folder rules

Preferred long-term folders:

```text
engine/
runtime/
reality-packs/
tools/
research/
demos/
docs/
```

Do not rename or move folders without updating:

- README
- SYSTEM_ARCHITECTURE
- relevant docs
- issue references if needed

## Code rules

- Keep MVP code simple and inspectable.
- Prefer clear names over clever abstractions.
- Separate data models from Unity scene behavior where practical.
- Do not hard-code `1812` and `3055` into core engine logic if a data-driven pack loader is feasible.
- Gracefully handle missing pack files, missing labels, and missing assets.
- Preserve a working demo path over architectural purity.

## Documentation rules

When making a non-trivial change, update the relevant doc.

When making an architectural decision, append to `DECISIONS.md`.

When adding terminology, update `TERMINOLOGY.md`.

## Safety/privacy rules

Do not add features that identify people, infer private traits, or upload camera data by default.

Respect `docs/05-privacy-safety.md`.

## Scope-control rule

Before adding a feature, ask:

1. Does it support the next demo?
2. Is it in the current phase?
3. Does it require new hardware?
4. Does it make future work easier or harder?
5. Is it documented?

If unclear, stop and ask.

## First implementation target

The first implementation target is:

> Same real place. Same geometry. Switch between neutral, 1812, and 3055.

Do not optimize for future glasses before this works on phone.
