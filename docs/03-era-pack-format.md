# 03 — Era Pack Format

## Purpose

An era pack defines how the live world should be visually reinterpreted.

It maps real-world labels to:

- Materials.
- Prefabs.
- Lighting behavior.
- Audio behavior.
- Optional effects.
- Optional educational/historical notes.

## Folder layout

```text
assets/era-packs/1812/
  manifest.json
  materials/
    dirt_road.png
    old_brick.png
    aged_wood.png
  prefabs/
    lantern.prefab
    wood_sign.prefab
  audio/
    ambient_town_loop.mp3
  notes/
    historical_context.md
```

## Manifest schema draft

```json
{
  "id": "1812",
  "display_name": "1812 Mode",
  "version": "0.1.0",
  "description": "Older-world town/street interpretation using dirt, brick, wood, lanterns, and muted signs.",
  "surface_rules": {
    "road": {
      "material": "materials/dirt_road.png",
      "overlay_opacity": 0.85,
      "height_offset": 0.01
    },
    "wall": {
      "material": "materials/old_brick.png",
      "overlay_opacity": 0.75,
      "height_offset": 0.02
    },
    "building": {
      "material": "materials/old_brick.png",
      "overlay_opacity": 0.70,
      "height_offset": 0.02
    },
    "sign": {
      "replacement_prefab": "prefabs/wood_sign.prefab",
      "overlay_opacity": 1.0
    }
  },
  "props": [
    {
      "id": "lantern",
      "prefab": "prefabs/lantern.prefab",
      "spawn_on": ["wall", "sign"],
      "max_count": 3
    }
  ],
  "lighting": {
    "temperature": "warm",
    "intensity_multiplier": 0.85,
    "fog": "light"
  },
  "audio": {
    "ambient_loop": "audio/ambient_town_loop.mp3",
    "volume": 0.35
  }
}
```

## Required fields

```text
id
display_name
version
description
surface_rules
```

## Surface rule fields

| Field | Type | Purpose |
|---|---|---|
| material | string | Texture/material path |
| replacement_prefab | string | Optional prefab replacement |
| overlay_opacity | number | Blend strength from 0 to 1 |
| height_offset | number | Offset to avoid z-fighting |
| effect | string | Optional shader/effect name |

## Label vocabulary

Start with this fixed label set:

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

Do not add too many labels early. The MVP needs reliability more than vocabulary size.

## Era pack examples

### 1812

```text
road      → dirt road
ground    → mud/grass mix
wall      → old brick / aged plaster
building  → brick / timber / plaster
sign      → painted wood
tree      → mostly unchanged, lower saturation
vehicle   → hide, ghost, or wrap as wagon placeholder
sky       → warmer, smoky, muted
```

### 3055

```text
road      → glowing transit grid
ground    → clean composite material
wall      → glass/carbon/metal
building  → megastructure skin
sign      → holographic panel
tree      → bioluminescent or synthetic vegetation
vehicle   → autonomous pod overlay
sky       → orbital lanes / drone trails
```

## Creator-pack direction

Later, creators should be able to build packs without editing app code.

Future creator tool flow:

1. Choose base era.
2. Upload or generate textures.
3. Define surface rules.
4. Preview on test scene.
5. Export pack.
6. Share/sell/free-distribute through a library.

## Rule

An era pack should never require the real world to be perfectly scanned. It should degrade gracefully with partial geometry.
