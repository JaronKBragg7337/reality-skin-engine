# Scene Understanding Notes

## Problem

Reality Skin Engine needs to understand enough of the world to apply the right visual interpretation.

It does not need perfect intelligence at first.

## Levels of scene understanding

### Level 0 — No understanding

The app places generic AR objects.

Not enough for Reality Skin Engine.

### Level 1 — Plane detection

The app understands flat surfaces.

Good enough for first prototype.

### Level 2 — Manual semantic labels

The user labels a surface as road, wall, sign, ground, etc.

This is the MVP target.

### Level 3 — Assisted labels

The app suggests labels, the user confirms.

This is the best second-stage path because it avoids blind trust in AI recognition.

### Level 4 — Automatic labels

The app labels surfaces/objects automatically.

Useful later, but not required early.

### Level 5 — Persistent world model

The app remembers a place and its labels across sessions.

This becomes important for tourism, museums, and city-scale packs.

## MVP data structure

```json
{
  "scene_id": "local-test-scene",
  "surfaces": [
    {
      "id": "surface-001",
      "label": "wall",
      "anchor_id": "anchor-001",
      "era_overrides": {},
      "confidence": "manual"
    }
  ]
}
```

## Semantic labels

Start with:

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

## Important distinction

A surface label is not the same as an object identity.

Example:

```text
Correct early label: building
Avoid early label: CVS at 123 Main Street
```

The MVP should avoid identity-level recognition.

## Person handling

People should be treated as protected dynamic objects.

Early behavior:

- Do not reskin people.
- Do not identify people.
- Do not place opaque overlays over people.

## Practical method

For each detected plane or proxy mesh:

1. User taps surface.
2. App shows label menu.
3. User picks label.
4. App stores anchor + label.
5. EraSkinManager applies era rule.

## Later assisted-label pipeline

```text
Camera frame
  → local vision model or cloud vision call
  → candidate labels
  → user confirmation
  → local scene label stored
```

## Rule

Manual labeling is not a weakness. It is a way to prove the core product without waiting for perfect AI.
