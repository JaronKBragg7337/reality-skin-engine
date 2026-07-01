# Design Principles

## 1. Geometry is truth

The physical world is the grounding layer.

Walls, roads, stairs, doors, signs, people, vehicles, and hazards must remain respected even when visually reinterpreted.

## 2. Interpretation is replaceable

The same geometry can support many interpretations.

```text
same wall
  -> 1812 brick
  -> 3055 glass/carbon
  -> blueprint grid
  -> museum label overlay
  -> fantasy stone
```

## 3. Displays are clients

The engine should not be designed around one display device.

Phone first. Headset later. Glasses later. Future display clients possible.

## 4. Reality Packs are data

Reality Packs should define interpretation rules without requiring core code changes.

The engine should load packs, validate packs, and apply pack rules.

## 5. Engine first, hardware later

Do not wait for glasses, wearables, EEG, or custom sensors to prove the core engine.

The engine must work before advanced devices matter.

## 6. Manual first, AI-assisted later

Manual labeling is acceptable and strategic for the MVP.

Automatic scene understanding can be added once the core loop works.

## 7. Preserve physical safety

Visual overlays must not hide hazards.

People, stairs, traffic, exits, and safety signals need protective handling.

## 8. Local-first by default

Do not upload camera data, scene meshes, location history, or biosignals by default.

## 9. Build observable capability

Every phase should create a concrete artifact:

- code
- demo
- video
- schema
- doc
- issue
- test result
- decision log

## 10. One demo beats ten concepts

The first milestone is not completeness. It is proof.

> Same real place. Same geometry. Different rendering.

## 11. Future layers stay visible but non-blocking

Wearables, AR glasses, persistent city maps, creator marketplaces, and AI-generated live worlds remain valid future layers.

They are not current dependencies unless explicitly promoted into scope.

## 12. Architecture should enable many apps

Do not trap the engine inside one demo application.

The engine should support multiple applications over time.
