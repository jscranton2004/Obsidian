# Stellar Hegemony - Phase 2: Leader Selection Flow

**Date:** 2026-05-30  
**Status:** Planning

## Goal
Connect the existing `LeaderSelection` logic to a minimal UI so players can draft leaders at the start of a game.

## Current State
- `LeaderSelection` system is complete (pure logic)
- 6 leaders with exact names and titles are defined
- Rules for player count + 1, reverse turn order drafting, and random exclusion are implemented
- No UI or game-start integration currently exists

## Phase 2 Objectives

1. **Leader Selection UI** (Minimal)
   - Simple interface to display offered leaders
   - Allow players to pick in the correct order (reverse turn order)
   - Show which leader was excluded

2. **Game Start Integration**
   - Wire leader selection into the start of a new game
   - Store selected leaders on `PlayerState`

3. **Basic Flow**
   - Start game → Determine players → Show leader draft → Proceed to deployment phase

## Recommended Task Order

| Order | Task | Scope | Priority |
|-------|------|-------|----------|
| 1     | Build minimal Leader Selection UI | Medium | High |
| 2     | Wire leader draft into game start flow | Narrow | High |
| 3     | Store selected leaders on PlayerState | Narrow | Medium |
| 4     | Documentation update for Phase 2 | - | Medium |

## Out of Scope (for this phase)
- Actual leader card effects
- Full Player model beyond leader selection
- Faction selection visuals
- Any gameplay after deployment

## Success Criteria
- Players can go through a leader draft at the start of a game
- Draft follows the correct rules (reverse order, one leader excluded)
- Selected leaders are remembered for the game

---
*This note will be updated as tasks are completed.*