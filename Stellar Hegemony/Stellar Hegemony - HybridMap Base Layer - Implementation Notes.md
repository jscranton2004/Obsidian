# Stellar Hegemony - HybridMap Base Layer - Implementation Notes

**Implemented:** 2026-05-30 by Grok Build  
**Status:** Complete (narrow scope)  
**Related:** [[Stellar Hegemony - Map System (Hybrid Approach)]]

## What Was Delivered

### Files Created
- `game/scenes/Map/HybridMap.tscn`
  - Root `Node3D` named `HybridMap`
  - `MeshInstance3D` (`NebulaBasePlane`) using a `PlaneMesh` sized at **5120 × 1440** units
  - `WorldEnvironment` + `DirectionalLight3D` with retro atompunk styling
- `game/shaders/nebula_starfield.gdshader`
  - Procedural nebula + starfield shader in 1950s retro Jetson style
- `game/materials/NebulaStarfield.tres`
  - Material resource using the new shader

### Key Design Decisions
- Plane size matches the 32:9 ultrawide target from the canonical map reference
- Shader kept performant for Steam Deck
- Scene structured to easily accept multiple `Zone.tscn` instances on top
- Visual foundation only — no interaction or zone logic added

## Testing Instructions
1. Open `HybridMap.tscn` in the Godot editor
2. Run the scene (F5/F6)
3. Use an OrbitCamera and pull back ~15–25 units
4. Verify the nebula plane renders correctly with swirling retro colours and twinkling stars
5. Confirm performance stays in the 40–60 fps range on modest hardware
6. Check that `NebulaBasePlane.mesh.size` = `(5120, 1440)`

## Assumptions Made
- World scale of 5120 × 1440 units is correct
- Focus was kept strictly on the visual base layer
- Godot 4.6.3 Forward+ renderer
- No height variation or noise was added to the plane (kept flat for now)

---

*Clean, narrow-scope implementation that gives us a solid foundation to build the zones on top of.*