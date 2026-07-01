# Contributing

## Project purpose

Reality Skin Engine is a rendering engine for reality. Contributions should strengthen the engine, the Unity runtime, the Reality Pack system, the documentation, or the demo path.

## Current priority

The current priority is the phone-based MVP:

```text
AR phone camera
  -> detect surface
  -> label surface
  -> load Reality Pack
  -> apply visual interpretation
  -> switch between neutral, 1812, and 3055
```

## Contribution types

Useful contributions:

- Unity AR Foundation setup
- ARCore/ARKit runtime support
- surface labeling UI
- Reality Pack loader
- pack schema validation
- placeholder materials and props
- Blender/Maya/Substance asset pipeline
- docs and diagrams
- test plans
- demo scripts

Avoid for now:

- custom hardware dependencies
- EEG/wearables implementation
- multiplayer architecture
- marketplace architecture
- perfect AI object recognition
- large speculative rewrites

## Branching

Use short descriptive branch names:

```text
feature/arcore-plane-detection
feature/reality-pack-loader
feature/manual-label-ui
docs/project-boundaries
fix/pack-loader-missing-label
```

## Commit style

Use clear commit messages:

```text
Add ARCore plane detection scene
Implement Reality Pack manifest parser
Document project boundaries
Fix missing label fallback
```

## Pull request checklist

Before opening or merging a PR:

- Does it support the current MVP or documented roadmap?
- Does it avoid unnecessary future-phase dependencies?
- Does it keep phone MVP working?
- Are docs updated if architecture changed?
- Are new terms added to `TERMINOLOGY.md`?
- Are major decisions added to `DECISIONS.md`?

## Documentation expectations

Every major feature should have at least one of:

- a doc update
- a decision log entry
- an issue explaining the purpose
- a test note or demo note

## Asset expectations

For generated or sourced assets:

- keep files organized by Reality Pack
- prefer low-poly and lightweight materials early
- document source/licensing when relevant
- avoid huge binary files until the repo strategy is decided

## Privacy/safety expectations

Do not add default camera upload, face identification, bystander recognition, or hidden location logging.

The MVP should stay local-first.

## Final rule

Preserve the demo path. The first working demo matters more than speculative completeness.
