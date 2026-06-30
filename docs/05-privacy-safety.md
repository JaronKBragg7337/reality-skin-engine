# 05 — Privacy and Safety Baseline

## Purpose

Reality Skin Engine uses cameras, spatial mapping, and potentially wearable/context signals. That creates privacy and safety obligations even in a prototype.

This document is not meant to slow the build. It is meant to prevent avoidable mistakes that would break trust or block deployment later.

## Default privacy posture

For the MVP:

- Process camera/spatial data locally when possible.
- Do not upload camera footage by default.
- Do not store raw camera footage unless the user explicitly records a demo.
- Do not store location unless needed for a specific feature.
- Do not identify bystanders.
- Do not build face recognition.
- Do not infer private traits from people in view.

## Data classes

### Low sensitivity

- Era selection.
- App settings.
- Generic surface labels such as road/wall/sign.
- Local non-identifying debug logs.

### Medium sensitivity

- Scene mesh.
- Depth map.
- Persistent anchors.
- Location-specific packs.
- Voice commands.

### High sensitivity

- Raw camera footage.
- Home interior scans.
- Faces/bystanders.
- Precise location history.
- Wearable biometrics.
- EEG or neural-adjacent signals.

## MVP storage rule

Store only what is needed for local testing:

```text
Allowed:
- selected era
- manually labeled surface anchors
- local test scene settings

Avoid:
- raw camera recordings
- location history
- people identification
- cloud uploads
```

## Physical safety

AR overlays must not hide real hazards.

Do not obscure:

- Cars.
- People.
- Stairs.
- Doors/exits.
- Fire alarms.
- Emergency signs.
- Holes/drop-offs.
- Traffic signals.
- Active machinery.

For early prototypes, use a visible passthrough blend and avoid full-opacity overlays in outdoor/high-risk areas.

## Bystander rule

The app should treat people as protected objects.

Initial behavior:

- Do not reskin real people.
- Do not label real people beyond generic `person` if a future detector exists.
- Do not record or upload bystander footage without user/legal consent.

## Location rule

Location-aware historical packs are valuable, but location should be explicit.

Initial behavior:

- No background location tracking.
- No automatic location upload.
- Let the user choose a demo location manually.

## Wearable/EEG rule

Wearable signals are later-layer inputs, not MVP requirements.

If added later:

- Treat biosignals as high sensitivity.
- Store raw data only with explicit user intent.
- Prefer derived local states over raw uploads.
- Make controls transparent and reversible.

## Content safety

Era packs should avoid presenting speculative content as confirmed history.

Historical pack labels:

```text
Historical reconstruction
Speculative reconstruction
Fictional interpretation
Fantasy mode
Future concept
```

## Build rule

Do not use privacy/safety as an excuse to shrink the idea prematurely. Use it as a design layer that keeps the project deployable.
