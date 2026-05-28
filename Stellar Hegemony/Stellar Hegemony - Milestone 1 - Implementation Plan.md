# Stellar Hegemony - Milestone 1: Implementation Plan

**Status:** Detailed Planning  
**Date:** 2026-05-28  
**Related:** [[Stellar Hegemony - Milestone 1 - Clickable Territory Prototype]]

## 1. Project Structure (Godot 4)

```
stellar-hegemony/
├── game/
│   ├── scenes/
│   │   ├── Main.tscn                 # Root scene
│   │   ├── Map/
│   │   │   ├── HybridMap.tscn
│   │   │   └── Zone.tscn             # Reusable zone template
│   │   └── Camera/
│   │       └── OrbitCamera.tscn
│   ├── scripts/
│   │   ├── map/
│   │   │   ├── hybrid_map.gd
│   │   │   └── zone.gd
│   │   ├── systems/
│   │   │   └── dice_deployment.gd
│   │   └── ui/
│   │       └── deployment_ui.gd
│   ├── shaders/
│   │   └── nebula_starfield.gdshader
│   ├── assets/
│   │   └── materials/
│   └── autoloads/
│       └── GameManager.gd
```

## 2. Core Scenes & Nodes

### HybridMap.tscn
- `Node3D` (root)
  - `MeshInstance3D` — Base Nebula Plane (large PlaneMesh + ShaderMaterial)
  - Multiple `Zone.tscn` instances (positioned in a loose cluster)
  - `WorldEnvironment`
  - `DirectionalLight3D`

### Zone.tscn (reusable)
- `Node3D`
  - `MeshInstance3D` — Zone mesh (slightly raised plane or low-poly shape)
  - `Area3D` + `CollisionShape3D`
  - `Label3D` or `SubViewport` for unit count / ownership
  - Script: `zone.gd`

### OrbitCamera.tscn
- `Camera3D` with custom orbit/pan script (smooth controls, boardgame-friendly distance)

## 3. Shader Approach (Base Layer)

**File:** `nebula_starfield.gdshader`

- Fragment shader using `fbm` (fractal Brownian motion) for nebula clouds
- Scattered point stars with subtle twinkling
- Retro 1950s colour palette (deep indigo/purple + cyan/magenta accents)
- Parameters exposed for:
  - Nebula colour
  - Star density
  - Twinkle speed
  - Overall brightness

The base plane uses this shader. Individual zones can use the same shader with different seed/colour uniforms for visual variety.

## 4. Task Breakdown (for Grok Build CLI)

### Phase 1: Foundation
1. Create new Godot 4 project with correct folder structure
2. Set up `Main.tscn` with basic 3D environment
3. Create the procedural `nebula_starfield.gdshader`
4. Build `HybridMap.tscn` with base plane + 6–8 zone instances

### Phase 2: Zones & Interaction
5. Create `Zone.tscn` template with `Area3D`
6. Implement `zone.gd` (highlight on hover, selection, ownership, unit count)
7. Implement basic mouse picking and zone selection

### Phase 3: Dice Deployment System
8. Create `dice_deployment.gd` autoload or node
9. Implement split-dice logic (2d6 for zone selection, 1d6 for quantity)
10. Visual feedback when a zone is targeted by dice
11. Place units in the selected zone

### Phase 4: Camera & Polish
12. Implement `OrbitCamera` with good controls
13. Add simple UI for "Roll & Deploy" and "End Turn"
14. Apply initial retro styling (materials, lighting, colours)
15. Basic ownership colour tinting on zones

## 5. Success Criteria (Technical)

- Player can press a button to roll dice
- The correct zone is highlighted based on the 2d6 sum
- The correct number of units visually appear in that zone
- The hybrid map renders nicely with the procedural shader
- Camera feels good for a boardgame view

## 6. Hand-off Strategy

We will break the above phases into small, self-contained tasks that can be handed to Grok Build CLI one at a time, with Hermes reviewing each piece before moving to the next.

---

**Next Action:** Once approved, begin Phase 1 Task 1 (project setup + shader).