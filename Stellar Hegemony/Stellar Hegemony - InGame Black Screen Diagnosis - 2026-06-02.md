# Stellar Hegemony - InGame Black Screen Diagnosis (2026-06-02)

**Status:** Senior-level analysis after full repo pull  
**Author:** Ron (Hermes) — acting as senior game developer

## Summary
After pulling the latest state of the repo, a thorough review of `InGame.tscn`, `in_game.gd`, `orbit_camera.gd`, `HybridMap.tscn`, and related files reveals several structural issues that are very likely causing the persistent black screen (both 3D and 2D).

## Key Findings

### 1. Root Node Type is `Node3D` (Highest Probability Cause)
- `scenes/levels/InGame.tscn` has `Node3D` as its root.
- This is problematic when the scene also contains a `CanvasLayer` + `Control`-based HUD.
- Common issues with `Node3D` roots + `CanvasLayer`:
  - UI not rendering or appearing off-screen
  - Viewport scaling problems
  - `CanvasLayer` behavior becoming unreliable

### 2. HUDPanel Has Weak Anchoring
- `HUDPanel` uses `anchors_preset = 1` with fixed pixel offsets (`offset_left = -320`, `offset_right = -20`).
- This creates a fixed-size panel rather than a properly responsive one.
- Combined with the `Node3D` root, this is very likely why no UI elements are visible.

### 3. WorldEnvironment Placement
- `WorldEnvironment` only exists inside the instanced `HybridMap.tscn`.
- No environment is defined at the `InGame` scene root level.
- This can result in a completely black 3D view even when geometry exists.

### 4. Camera & System Initialization
- `orbit_camera.gd` correctly sets `current = true` and calls `_setup_initial_view()`.
- `in_game.gd` initializes all managers after the camera’s `_ready()`.
- No obvious logic errors found in camera or manager setup.

### 5. Other Areas Checked
- Zone creation is working (confirmed in logs).
- Node paths in `in_game.gd` match the scene structure.
- `CanvasLayer` layer is at default (0).

## Recommended Next Steps (Narrow Scope)
1. Change `InGame.tscn` root from `Node3D` to `Node`.
2. Improve `HUDPanel` anchoring (use `Full Rect` or proper anchors).
3. Add or promote a `WorldEnvironment` to the `InGame` scene level.
4. Verify camera remains active after these structural changes.

## References
- [[Stellar Hegemony - Handoff Note - 2026-06-02]]
- [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

---

*This note was created after a full `git pull` and manual inspection of the live project files.*