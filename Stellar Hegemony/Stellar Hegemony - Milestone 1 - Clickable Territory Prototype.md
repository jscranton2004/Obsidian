# Stellar Hegemony - Milestone 1: Clickable Territory Prototype

**Status:** Planned  
**Date:** 2026-05-28  
**Goal:** First playable slice that demonstrates the hybrid map + core dice deployment mechanic.

## Milestone Objective
Create a minimal but real playable prototype featuring:
- The hybrid map system (procedural nebula floor + individual zones)
- Dice-based zone selection and force deployment (core tension from the rules)
- Basic camera and interaction
- Visual feedback for selection and unit placement

This milestone validates both the visual direction and the fundamental gameplay loop before adding combat, cards, or full rules.

## Key Features to Implement

### 1. Hybrid Map Foundation
- Large base plane with procedural nebula + starfield shader (1950s Jetson retro style)
- 6–8 individual zone meshes on top (using the hybrid approach)
- Each zone has its own `Area3D` + material instance

### 2. Camera & Scene
- Orbit/pan camera with good controls for a boardgame view
- Clean retro-styled lighting and environment

### 3. Dice Deployment System (Core Mechanic)
- Simulate the split-dice deployment:
  - Two dice determine the target zone (sum)
  - One die determines quantity of forces placed
- Visual feedback when a zone is targeted
- Units appear in the selected zone

### 4. Basic Interaction & Feedback
- Clickable/highlightable zones
- Simple ownership and unit count display (labels or floating UI)
- "Roll & Deploy" and "End Turn" actions

### 5. Art & Styling Direction
- Apply initial retro 1950s space aesthetic to the map and zones
- Keep everything feeling like a physical boardgame in space

## Out of Scope (for this milestone)
- Wormholes
- Combat resolution
- Tactic / Leader cards
- Multiple players
- Full game loop or win conditions

## Success Criteria
- Player can roll dice, see a zone selected, and see forces appear in that zone
- The hybrid map looks and feels good
- The prototype feels like the beginning of a real game

## Next Steps After This Milestone
- Expand to full deployment phase
- Add wormhole connections
- Begin adapting the first Tactic Cards

---
**Related Notes:**
- [[Stellar Hegemony - Map System (Hybrid Approach)]]
- [[Stellar Hegemony - Core Mechanics]]