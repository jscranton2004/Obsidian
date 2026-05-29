# Stellar Hegemony - Exhaustion Order Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define how player exhaustion is tracked and how exhaustion order determines tiebreakers.

## Overview

In Stellar Hegemony, players become "exhausted" when they run out of deployable units. The **order** in which players exhaust is important because it grants **tiebreaker priority** during the War phase.

## Core Rules

### What Causes Exhaustion
- A player becomes exhausted when they have **zero units left** in their pool (all fleets + flagship have been placed or removed).
- This can happen during Deployment or as a result of card effects / combat losses.

### Exhaustion Order
- The game tracks the **sequence** in which players exhaust.
- Players who exhaust **earlier** receive **higher tiebreaker priority** in the War phase.
- The first player to exhaust has the strongest tiebreaker advantage.
- Players who never exhaust (still have units at game end) have the lowest priority.

### Tiebreaker Application
- During War phase resolution, when two or more players have the same total strength in a zone, the player with the **better exhaustion order** (earlier exhaustion) wins the tie.
- This replaces or supplements other tiebreakers (such as leader abilities).

### Tracking Requirements
- Record the exact turn number (or global turn count) when each player exhausts.
- Store the order as a ranked list (1st exhausted, 2nd exhausted, etc.).
- Once a player is marked exhausted, their position in the order is locked.

## Scope for Initial Implementation

- Create a system to detect when a player reaches zero units.
- Record the exhaustion timestamp / order.
- Provide query methods for tiebreaker comparison (`get_exhaustion_priority(player_id)`).
- Integrate with `PlayerState` (which already tracks token pools).
- Do **not** implement War phase resolution yet.

## Integration Points

- Should listen to `PlayerState` pool changes.
- Should work with the existing `TurnManager` (which already calls `lock_pool_for_exhaustion()`).
- Should be queryable by future War / Scoring systems.

## References

- `Stellar Hegemony - Turn Structure Design.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`
- `Stellar Hegemony - Core Mechanics.md`

---

*This system provides a clear, fair tiebreaker mechanism based on resource management.*