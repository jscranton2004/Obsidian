# Stellar Hegemony - Phase 3: Core Gameplay Systems

**Date:** 2026-05-30  
**Status:** Planning

## Goal
Build the core gameplay systems that turn the current deployment experience into a real strategy game.

## Current State
- Leader selection and deployment phase are functional
- Zones support ownership and unit visuals
- Connectivity system (hyperspace + wormhole) exists in `HybridMap`
- No movement or combat systems yet

## Phase 3 Objectives

1. **Basic Movement**
   - Allow fleets to move between connected zones using the existing connectivity queries
   - Support both hyperspace and wormhole movement rules

2. **Zone Control**
   - Basic zone ownership changes when units are moved or combat occurs
   - Simple control scoring at end of game (or turn)

3. **Simple Combat**
   - Basic combat resolution when units from different factions occupy the same zone
   - Keep it minimal (power comparison + possible reinforcements)

## Recommended Task Order

| Order | Task | Scope | Priority |
|-------|------|-------|----------|
| 1     | Basic fleet movement using connectivity | Medium | High |
| 2     | Simple zone control / ownership updates | Narrow | High |
| 3     | Minimal combat resolution | Medium | High |
| 4     | Documentation update for Phase 3 | - | Medium |

## Out of Scope (for this phase)
- Full card effects
- Advanced combat (exhaustion order, etc.)
- AI opponents
- Victory conditions and scoring screen

## Success Criteria
- Players can move units between zones using hyperspace and wormholes
- Moving into an enemy-controlled zone triggers basic combat
- Zone ownership updates correctly

---
*This note will be updated as tasks are completed.*