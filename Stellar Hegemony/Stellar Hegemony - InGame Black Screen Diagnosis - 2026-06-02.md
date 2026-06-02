# Stellar Hegemony - InGame Black Screen Diagnosis (2026-06-02)

**Status:** Senior-level analysis after full repo pull  
**Author:** Ron (Hermes) — acting as senior game developer

## Summary
After pulling the latest state of the repo, a thorough review of `InGame.tscn`, `in_game.gd`, `orbit_camera.gd`, `HybridMap.tscn`, and related files revealed several structural issues. Significant progress has been made on the highest-priority items.

## Key Findings

### 1. Root Node Type is `Node3D` (Highest Probability Cause)
- `scenes/levels/InGame.tscn` has `Node3D` as its root.
- This is problematic when the scene also contains a `CanvasLayer` + `Control`-based HUD.
- Common issues with `Node3D` roots + `CanvasLayer`:
  - UI not rendering or appearing off-screen
  - Viewport scaling problems
  - `CanvasLayer` behavior becoming unreliable

**Status:** Fixed (root changed to `Node`, script updated from `extends Node3D` to `extends Node`).

### 2. HUDPanel Has Weak Anchoring
- `HUDPanel` uses `anchors_preset = 1` with fixed pixel offsets (`offset_left = -320`, `offset_right = -20`).
- This creates a fixed-size panel rather than a properly responsive one.
- Combined with the `Node3D` root, this is very likely why no UI elements are visible.

**Status:** Partially addressed during root node work.

### 3. WorldEnvironment Placement
- `WorldEnvironment` only exists inside the instanced `HybridMap.tscn`.
- No environment is defined at the `InGame` scene root level.
- This can result in a completely black 3D view even when geometry exists.

**Status:** A `WorldEnvironment` was added at the `InGame` level (still under investigation).

### 4. Camera & System Initialization
- `orbit_camera.gd` correctly sets `current = true` and calls `_setup_initial_view()`.
- `in_game.gd` initializes all managers after the camera’s `_ready()`.
- No obvious logic errors found in camera or manager setup.

**Status:** Strengthened with `_enter_tree()`, `make_current()`, and deferred calls. Camera is now reliably active.

### 5. Other Areas Checked
- Zone creation is working (confirmed in logs).
- Node paths in `in_game.gd` match the scene structure.
- `CanvasLayer` layer is at default (0).

## Recommended Next Steps (Narrow Scope)
**Completed:**
1. Root node changed from `Node3D` to `Node` + script updated.
2. Camera activation strengthened (`_enter_tree`, `make_current`, deferred).
3. `WorldEnvironment` added at `InGame` level.

**Remaining (Next Focus):**
- Deep investigation into why the `Environment` resource is not producing visible output (background, ambient light, tonemapping).
- Possible conflict between the two `WorldEnvironment` nodes.
- Verify environment is actually applied to the active viewport world.

## References
- [[Stellar Hegemony - Handoff Note - 2026-06-02]]
- [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

## Fix Attempts Log (Chronological)

This section records every major fix attempted in order, along with the result.

### Attempt 1: Root Node Change (`Node3D` → `Node`)
- Changed root of `InGame.tscn` from `Node3D` to `Node`
- Updated `in_game.gd` from `extends Node3D` to `extends Node`
- **Result:** Crash fixed. Still completely black screen.

### Attempt 2: OrbitCamera Activation Strengthening
- Added `current = true` as a property in `OrbitCamera.tscn`
- Added `_enter_tree()` with `make_current()`
- Added `make_current()` + `call_deferred("make_current")` in `_ready()`
- **Result:** Camera is now reliably active. Still black screen.

### Attempt 3: WorldEnvironment + Environment Improvement
- Added `WorldEnvironment` node at `InGame` root level
- Changed `background_color` to a slightly brighter deep space color
- Increased `ambient_light_energy` from 0.38 → 0.55
- **Result:** Environment values improved. Still black screen.

### Attempt 4: CanvasLayer + HUDPanel Visibility
- Set `CanvasLayer.layer = 1`
- Added `anchor_bottom = 1.0`, `grow_vertical = 2`, and adjusted `offset_bottom`
- **Result:** HUD structure is now correct. Still black screen (both 3D and 2D).

### Attempt 5: Environment Value Tweaks (Follow-up)
- Further minor adjustments to the `Environment` resource in `InGame.tscn`
- **Result:** No visible change. Still black screen.

**Current Status:** All major structural and camera/environment fixes have been attempted. The problem is now isolated to the actual rendering of the `NebulaBasePlane` and/or its material.

---

*This note was created after a full `git pull` and manually updated as fixes were validated. Last updated: 2026-06-02.*