# Stellar Hegemony - InGame Black Screen Diagnosis (2026-06-02)

**Author:** Ron Weasley (Senior Analysis)  
**Status:** Detailed Technical Assessment  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-02]], [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

## Executive Summary

After pulling the latest repository state and performing a thorough review of the project, the root cause of the persistent black screen (no 3D map and no visible HUD) when entering `InGame.tscn` has been identified. The issue is **architectural** rather than a simple camera positioning problem.

The combination of using `Node3D` as the root of `InGame.tscn` while also hosting a `CanvasLayer` + `Control`-based HUD is causing both the 3D rendering and 2D UI to fail to display.

## Detailed Findings

### 1. Critical Issue: Root Node Type (`Node3D`)

**Location:** `scenes/levels/InGame.tscn`

```tscn
[node name="InGame" type="Node3D"]
script = ExtResource("1_in_game")
```

**Analysis:**
- Using `Node3D` as the root for a scene that contains both 3D content **and** a full `CanvasLayer` HUD is highly problematic in Godot 4.
- This setup frequently causes `CanvasLayer` to behave unpredictably.
- Viewport scaling, stretch mode, and UI anchoring become unreliable when the root is not a `Control` or `Node`.
- This is the most likely single cause of **both** the black 3D view and missing HUD elements.

**Recommendation:** Change root to `Node` (or `Control` if heavy UI work is expected).

### 2. Weak HUD Anchoring & Sizing

**Location:** `scenes/levels/InGame.tscn` (HUDPanel)

```tscn
[node name="HUDPanel" type="Panel" parent="CanvasLayer"]
anchors_preset = 1
anchor_left = 1.0
anchor_right = 1.0
offset_left = -320.0
offset_top = 20.0
offset_right = -20.0
offset_bottom = 220.0
```

**Analysis:**
- The panel uses fixed pixel offsets instead of proper `Full Rect` or percentage-based anchoring.
- With a `Node3D` root, the Control may have zero effective size or be positioned off-screen.
- This explains why the HUD labels and button are completely invisible despite existing in the scene tree.

### 3. WorldEnvironment Placement

**Location:** `scenes/Map/HybridMap.tscn`

The `WorldEnvironment` node only exists inside the instanced `HybridMap` scene. When the root of `InGame.tscn` is `Node3D`, the environment may not apply correctly to the viewport.

This contributes to the completely black 3D rendering even when geometry (NebulaBasePlane + zones) is confirmed to exist via logs.

### 4. Camera & Environment Interaction

While the recent OrbitCamera fixes (`initial_distance = 50`, sign correction on pitch, `set_target` forcing `_reset_view`) are technically correct, they are fighting against the broken scene architecture. The camera may be active and positioned correctly, but the viewport/environment setup prevents it from rendering.

### 5. Other Areas Reviewed

| Component                  | Status     | Notes |
|---------------------------|------------|-------|
| `in_game.gd`              | Clean      | Logic and node paths are correct |
| `orbit_camera.gd`         | Good       | `_ready` + `current = true` + `_setup_initial_view` implemented |
| Zone creation             | Working    | Logs confirm 11 zones with correct values |
| `HybridMap` instantiation | Correct    | Properly added as child |
| `CanvasLayer` layer       | Default (0)| May need explicit layer value |

## Recommended Next Steps (Prioritized)

1. **Change `InGame.tscn` root from `Node3D` to `Node`** (highest impact)
2. Fix `HUDPanel` to use proper full-rect anchoring
3. Move or duplicate `WorldEnvironment` to the `InGame` scene root
4. Add explicit `make_current()` safety and environment configuration if needed
5. Verify rendering after the above changes

## Conclusion

This is no longer a camera positioning issue. It is a **scene architecture problem**. Continuing to tweak the OrbitCamera without addressing the root node type and environment setup will yield diminishing returns.

The project has reached a point where a structural correction in `InGame.tscn` is required before further camera or rendering work will be effective.

---

*This assessment was performed after a full `git pull` and direct inspection of the live project files.*