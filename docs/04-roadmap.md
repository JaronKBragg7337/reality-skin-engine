# 04 — Roadmap

## Phase 0 — Repository and planning

Goal: establish the project as a buildable repo, not just an idea.

Tasks:

- README.
- Vision doc.
- MVP blueprint.
- Stack/materials doc.
- Era-pack schema.
- Roadmap.
- Privacy/safety baseline.
- Initial GitHub issues.

Exit condition:

- A developer or AI coding agent can understand what to build first.

## Phase 1 — Phone AR MVP

Goal: prove the world-reskin loop on one phone.

Tasks:

- Create Unity project.
- Add AR Foundation.
- Add provider plugin: ARKit and/or ARCore.
- Detect planes.
- Tap-to-place overlay.
- Add manual surface labels.
- Add era selector UI.
- Load era-pack JSON.
- Apply materials/prefabs.
- Record demo.

Exit condition:

- Same real surface can visibly switch between `1812` and `3055`.

## Phase 2 — Better scene understanding

Goal: reduce manual tagging.

Tasks:

- Add depth where available.
- Add mesh reconstruction where available.
- Test object classification options.
- Add basic ML/vision labels if feasible.
- Store labeled surfaces in a local scene session file.

Exit condition:

- User can label less manually while app still applies correct skins.

## Phase 3 — Creator pack pipeline

Goal: make era packs easier to create and modify.

Tasks:

- Formalize manifest schema.
- Create validation script.
- Add sample packs.
- Add Blender export workflow.
- Add preview scene.
- Add pack thumbnails.

Exit condition:

- A creator can make a simple pack without changing app code.

## Phase 4 — Education/tourism demo

Goal: demonstrate a fundable non-game market.

Tasks:

- Pick one local/historical location.
- Build a simple location-specific historical pack.
- Add info cards.
- Add optional narration.
- Record before/after demo.

Exit condition:

- The project can be pitched to schools, museums, tourism boards, or local history groups.

## Phase 5 — Headset/glasses prototype

Goal: move beyond phone screen into mixed reality.

Tasks:

- Port Unity prototype to an XR headset where practical.
- Test passthrough mode.
- Test controller/hand input.
- Test stability, comfort, field of view, and battery limits.

Exit condition:

- A user can experience reality skins hands-free on available XR hardware.

## Phase 6 — Adaptive modes

Goal: connect the project to wearables and context.

Tasks:

- Voice command era switching.
- Eye/gesture switching where available.
- Optional biometrics input.
- Optional EEG/non-invasive sensor experiments.
- Mood/state-responsive skins.

Exit condition:

- The app can change skins based on user intent/context without manual UI taps.

## Long-term platform

Potential final form:

```text
Reality Skin Engine
  ├── Spatial understanding
  ├── Era/style packs
  ├── Creator tools
  ├── Education/tourism deployments
  ├── Game modes
  ├── Film/previs tools
  ├── Wearable control layer
  └── AR glasses/headset runtime
```

## Funding milestones

### Demo 1

Phone shows `1812` and `3055` skins on the same room or street.

### Demo 2

Location-specific historical experience.

### Demo 3

Creator creates a new pack without touching app code.

### Demo 4

Headset/glasses passthrough proof.

## Rule

Every phase must leave behind an artifact: code, demo, schema, pack, recorded video, issue, or decision log.
