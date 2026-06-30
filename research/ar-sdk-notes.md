# AR SDK Notes

## First SDK decision

Use Unity AR Foundation for the first prototype.

Reason:

- It abstracts ARKit and ARCore behind a Unity workflow.
- It supports common mobile AR concepts such as sessions, camera pose, plane detection, raycasts, and anchors.
- It lets the project start on phones before moving toward headsets or glasses.

## Important AR concepts

### Plane detection

Finds flat surfaces such as floors, walls, tables, and some outdoor ground surfaces.

MVP use:

- Let the user tap detected planes.
- Apply overlay textures.
- Spawn props on the plane.

### Raycast

Projects a tap/cursor from the screen into the AR scene.

MVP use:

- Tap-to-label.
- Tap-to-place.
- Tap-to-anchor props.

### Anchors

Attach virtual content to a real-world position.

MVP use:

- Keep overlays stable.
- Store labeled surfaces during a session.

### Depth

Estimates distance from the camera to real-world surfaces.

MVP use:

- Better occlusion.
- Better surface fit.
- Later: rough object boundaries.

### Scene mesh

A polygonal reconstruction of parts of the physical environment.

MVP use:

- Later phase only.
- Useful for more accurate wall/building skins.

## ARKit direction

ARKit is the Apple AR path for iPhone/iPad. Devices with LiDAR can support stronger depth and scene reconstruction features. This makes LiDAR Apple devices strong candidates for prototyping.

## ARCore direction

ARCore is the Google Android AR path. Device support varies, so testing should be done on a known ARCore-supported Android device if Android becomes the main target.

## OpenXR direction

OpenXR matters later when moving toward headset/glasses runtimes. It should not block the phone MVP.

## MVP risk list

| Risk | Mitigation |
|---|---|
| Outdoor plane detection is unstable | Test indoors first, then outdoors |
| Textures float or flicker | Use height offset and stable anchors |
| Device lacks LiDAR | Use plane detection and manual labels first |
| Object recognition is unreliable | Keep manual tagging in v0 |
| Too many era labels | Start with road/wall/sign/ground |
| App becomes too heavy | Use low-poly props and simple materials |

## Test locations

Start in controlled spaces:

1. Room wall + floor.
2. Sidewalk/building exterior.
3. Park/path/bench.
4. Street view only after safety pass.

## Main principle

Build against the device's actual capability. Do not design around unavailable glasses or untested SDK assumptions.
