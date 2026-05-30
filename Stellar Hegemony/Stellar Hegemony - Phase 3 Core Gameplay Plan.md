# Stellar Hegemony - Phase 3: Core Gameplay Systems

**Date:** 2026-05-30  
**Status:** Planning

## Goal
Build the core gameplay systems that turn the current deployment experience into a real strategy game.

## Current State
- Leader selection and deployment phase are functional
- Zones support ownership and unit visuals
- Connectivity system (hyperspace + wormhole) exists in `HybridMap`
- No War Phase or movement systems yet

## Phase 3 Objectives

1. **Basic Movement**
   - Allow fleets to move between connected zones using the existing connectivity queries
   - Support both hyperspace and wormhole movement rules
   - Movement is pure relocation only (no combat or ownership change on move)

2. **War Phase Resolution**
   - After all players finish deployment, resolve control of zones
   - The player with the most units in a zone gains control
   - Ties are broken by exhaustion order (the order in which players ran out of units)

3. **Zone Control**
   - Track zone ownership after War Phase resolution
   - Simple control scoring at end of game (or turn)

## Recommended Task Order

| Order | Task | Scope | Priority |
|-------|------|-------|----------|
| 1     | Basic fleet movement using connectivity | Medium | High |
| 2     | War Phase resolution system ("most units wins" + exhaustion order) | Medium | High |
| 3     | Zone ownership updates after War Phase | Narrow | High |
| 4     | Documentation update for Phase 3 | - | Medium |

## Out of Scope (for this phase)
- Full card effects
- Advanced combat mechanics
- AI opponents
- Victory conditions and scoring screen

## Success Criteria
- Players can move units between zones using hyperspace and wormholes (pure movement)
- After deployment, a War Phase resolves zone control using "most units wins"
- Exhaustion order is used as the tiebreaker for equal unit counts

---
*This note was corrected on 2026-05-30 to reflect the actual game rules (Deployment → War Phase).*