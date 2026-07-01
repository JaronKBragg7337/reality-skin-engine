# Engine

This folder is reserved for engine-level logic that should not be trapped inside one Unity scene or application.

## Purpose

The engine should eventually contain reusable logic for:

- Reality Pack loading
- Reality Pack validation
- surface labels
- surface rule resolution
- fallback behavior
- data models
- platform-independent interpretation logic

## Principle

Unity is the first runtime, not the entire engine.

Keep reusable logic here where practical. Runtime-specific code can live in `runtime/`.

## Early MVP note

It is acceptable for the first prototype to start inside Unity if that is faster. Once the logic stabilizes, reusable pack/schema code should move toward this engine layer.
