# Tools

Tools support Reality Pack creation, validation, asset processing, and build automation.

## Planned tools

```text
pack-validator
  Validate Reality Pack manifest files.

pack-preview
  Preview a Reality Pack in a controlled sample scene.

asset-pipeline
  Convert Blender/Maya/Substance outputs into Unity-ready assets.

demo-capture
  Organize screenshots, OBS captures, and FFmpeg edits.
```

## First tool to build

The first useful tool is a Reality Pack validator.

It should check:

- required fields exist
- surface rules use known labels
- material/prefab paths are valid when assets exist
- opacity values are between 0 and 1
- category/classification fields are present

## Principle

Tools should make creators and AI agents more reliable without slowing the MVP.
