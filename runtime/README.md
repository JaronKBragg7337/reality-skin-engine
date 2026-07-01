# Runtime

Runtime implementations run Reality Skin Engine on specific platforms.

## Current runtime target

The first runtime target is Unity:

```text
runtime/unity-prototype/
```

## Runtime principle

The runtime is not the whole project. It is one implementation client for the engine.

The runtime should:

- start AR sessions
- capture camera/pose/planes
- receive user input
- call engine/pack logic
- render overlays
- support demo recording

## Planned runtimes

```text
Unity phone runtime        current MVP
Unity headset runtime      later
Unreal cinematic runtime   later / optional
Native mobile runtime      future possibility
Glasses runtime            future possibility
```
