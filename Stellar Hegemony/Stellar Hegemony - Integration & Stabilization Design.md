# Stellar Hegemony - Integration & Stabilization Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define how to properly wire the existing managers together.

## Overview
We now have several powerful systems (`PlayerState`, `DeploymentManager`, `TacticManager`, `CardEffectExecutor`, `Zone Connectivity System`, etc.). The next priority is to integrate them so they work together cleanly instead of operating in isolation.

## Goals

### Primary Goals
- Make `TacticManager` automatically execute card effects via `CardEffectExecutor`
- Ensure `PlayerState` becomes the single source of truth for player data
- Remove/reduce manual `_and_execute` patterns
- Create clean communication paths between managers

### Secondary Goals
- Improve `CardExecutionContext` creation
- Prepare the foundation for a proper turn system

## Recommended Architecture

### Manager Relationships
- `DeploymentManager` → Owns `PlayerState` instances (source of truth)
- `TacticManager` → Should delegate to `CardEffectExecutor` when a player uses a tactic
- `CardEffectExecutor` → Reads from and writes to `PlayerState` via `CardExecutionContext`
- `HybridMap` → Provides zone and connectivity data

### Key Integration Points

1. **TacticManager → CardEffectExecutor**
   - `player_use_card()` should automatically call the executor if one is attached
   - The executor should receive a properly built `CardExecutionContext`

2. **PlayerState as Central Source**
   - All managers should read/write player data through `PlayerState` instead of raw dictionaries
   - `get_player_pool()` can remain for backward compatibility but should eventually delegate to `PlayerState`

3. **CardExecutionContext Factory**
   - Create a clean method to build a `CardExecutionContext` from the current game state (`DeploymentManager`, `HybridMap`, etc.)

## Scope for This Phase
- Focus on wiring and data consistency
- Do **not** implement full turn structure or War phase yet
- Keep changes minimal and safe

## References
- `Stellar Hegemony - PlayerState - Implementation Notes.md`
- `Stellar Hegemony - Card Effect Executor - Implementation Notes.md`
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md`

---

*This phase focuses on making the existing systems work together reliably.*