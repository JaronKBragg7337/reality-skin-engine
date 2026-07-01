# Architectural Decision Log

This file records major project decisions and why they were made.

## 2026-06-30 — Use phone AR before glasses

### Decision

Build the first prototype as a phone-based AR app before attempting AR glasses or custom hardware.

### Reason

Phones are available, affordable, testable, and already include camera, screen, motion sensors, and AR SDK support.

The engine must prove the core loop before hardware complexity is added.

### Tradeoff

The experience is less natural than glasses because the user must hold a phone.

### Consequence

AR glasses remain a future display client, not a current dependency.

---

## 2026-06-30 — Use Unity + AR Foundation for MVP

### Decision

Use Unity with AR Foundation as the first runtime implementation.

### Reason

Unity offers a mature mobile AR workflow and can target both ARCore and ARKit through provider plugins.

### Tradeoff

Unreal may offer stronger cinematic rendering later, but Unity is faster for the first phone AR MVP.

### Consequence

The first runtime lives in Unity. The engine concept should remain broader than Unity.

---

## 2026-06-30 — Use manual surface labeling first

### Decision

Use manual surface labels instead of depending on automatic AI object recognition in the MVP.

### Reason

Manual labeling proves the Reality Pack loop without blocking on unreliable or incomplete scene understanding.

### Tradeoff

The first demo is less automatic.

### Consequence

AI-assisted labeling becomes a later enhancement.

---

## 2026-07-01 — Rename Era Packs to Reality Packs

### Decision

Use `Reality Pack` as the main term for interpretation packs. Treat `Era Pack` as a historical subset or legacy term.

### Reason

The engine is broader than historical eras. It can support future, fantasy, accessibility, learning, mood, architecture, and creator packs.

### Tradeoff

Some early repository files still use `era-pack` wording and may need migration.

### Consequence

New docs and code should use Reality Pack terminology.

---

## 2026-07-01 — Treat wearables as Layer 3

### Decision

Wearables, EEG, EMG, biometrics, and distributed human-interface sensors are a later phase.

### Reason

They require additional hardware, materials, physical assembly, testing, and integration. They should not block the software engine proof.

### Tradeoff

The first prototype relies on phone UI/touch/voice rather than deeper human-interface systems.

### Consequence

Wearables remain visible in long-term architecture but out of MVP scope.

---

## 2026-07-01 — Android-first testing path

### Decision

Use Android/ARCore as the first physical test path because an Android test device is available and the main build machine is Windows.

### Reason

Direct local iPhone builds require macOS/Xcode or cloud build infrastructure. Android can be tested sooner after installing Unity Android Build Support.

### Tradeoff

iPhone/ARKit testing remains a second target.

### Consequence

Install Android Build Support, SDK/NDK, and OpenJDK first. Keep iOS Build Support as optional preparation.
