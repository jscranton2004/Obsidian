# Stellar Hegemony - Phase 1: Integration & Playable Core

**Date:** 2026-05-30  
**Status:** Planning  
**Focus:** Move from isolated systems to a basic playable core loop

## Goal
Integrate existing systems so that dice-based deployment actually works with zones on the map. This phase aims to deliver the first real "playable slice" of the game.

## Current State (as of 2026-05-30)

- HybridMap base layer + shader: Complete
- Zone template (`Zone.tscn` + `zone.gd`): Mature (hover, selection, ownership, unit visuals)
- HybridMap already instantiates 11 zones with positions and connectivity
- Dice deployment UI + logic: Exists
- Leader Selection, Turn Manager, Exhaustion, etc.: Logic exists but not integrated

## Phase 1 Objectives

1. **Dice → Zone Integration**
   - Wire dice results to zone targeting/highlighting
   - Allow player to confirm deployment into a selected zone
   - Update zone unit visuals (`fleet_count`, `has_flagship`) on deployment

2. **Basic Playable Loop**
   - Simple deployment phase flow
   - End of turn structure (even if minimal)
   - Visual feedback for unit placement

3. **System Connections**
   - Ensure `HybridMap` properly communicates with `Zone` instances
   - Clean up any integration gaps between existing managers

## Recommended Task Order

| Order | Task | Scope | Priority |
|-------|------|-------|----------|
| 1     | Wire dice deployment into zone selection + unit placement | Medium-narrow | High |
| 2     | Basic end-of-turn flow and state reset | Narrow | High |
| 3     | Clean integration between HybridMap and Zone | Narrow | Medium |
| 4     | Documentation update for Phase 1 | - | Medium |

## Out of Scope (for this phase)
- Leader selection UI
- Movement
- Combat
- Full game loop
- Polish / balancing

## Success Criteria
- Player can roll dice, select a zone, and see units appear on that zone
- The core deployment mechanic feels functional
- Code remains clean and well-documented

---
*This note will be updated as tasks are completed.*