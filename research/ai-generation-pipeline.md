# AI Generation Pipeline

## Purpose

Reality Skin Engine can use AI to help create era packs, textures, props, concept art, pitch videos, and eventually adaptive world skins.

AI should not be required for every frame of the MVP. The early app should use prebuilt/generated assets loaded from era packs.

## Recommended pipeline

```text
Reference idea
  → concept image
  → texture/material generation
  → Blender prop/blockout
  → Unity prefab/material
  → era-pack manifest
  → AR test
```

## Use cases

### Textures

Generate or source:

- Dirt road.
- Old brick.
- Weathered wood.
- Aged plaster.
- Glowing transit grid.
- Glass/carbon panel.
- Hologram panel.

### Props

Create simple props:

- Lantern.
- Torch.
- Wood sign.
- Wagon proxy.
- Drone light.
- Holographic sign.
- Future pod proxy.

### Pitch media

Create:

- Before/after concept images.
- Explainer diagrams.
- Short demo edits.
- Investor deck visuals.

## Blender workflow

For MVP props:

1. Create low-poly prop in Blender.
2. Assign simple materials.
3. Export as `.fbx` or `.glb`.
4. Import into Unity.
5. Turn into prefab.
6. Reference prefab in era-pack manifest.

## Agent workflow

Use AI coding agents for:

- Unity script generation.
- Manifest loader.
- Surface label UI.
- Material mapping.
- Build error debugging.
- Test scripts.
- Documentation.

Do not let agents freely change the whole project without a task boundary.

## Recommended first agent task

```text
Create a Unity C# script named EraPackLoader that reads a JSON era-pack manifest from StreamingAssets, parses surface_rules, and exposes a method GetRuleForLabel(string label).
```

## Recommended second agent task

```text
Create a Unity C# script named SurfaceLabelManager that lets a user tap an AR plane, choose a label from a UI menu, and stores the label with the AR anchor.
```

## Recommended third agent task

```text
Create a Unity C# script named EraSkinManager that applies materials or prefabs from the active era pack to labeled AR surfaces.
```

## Principle

Use AI generation to compress asset creation and coding time. Do not make the prototype dependent on live AI calls until the static asset pipeline works.
