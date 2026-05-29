# Stellar Hegemony - Exhaustion Order - Implementation Notes

**Status:** Complete  
**Date:** 2026-05-29  
**Related Design:** `Stellar Hegemony - Exhaustion Order Design.md`

## What Was Built

Grok Build delivered a clean, well-integrated Exhaustion Order system.

### Changes Made

**`player_state.gd`** (extended)
- New fields: `exhaustion_turn`, `exhaustion_rank`
- New signal: `exhausted(player_id)`
- New helper: `mark_exhausted(turn_number, rank)`
- Updated `_to_dict()` and `_check_and_mark_exhaustion()`

**New file: `exhaustion_manager.gd`**
- `ExhaustionManager` class with full query API:
  - `is_player_exhausted(player_id)`
  - `get_exhaustion_rank(player_id)`
  - `compare_exhaustion_priority(a, b)`
- Handles rank assignment (1 = first exhausted = best tiebreaker)
- Maintains a turn counter and records exhaustion
- Clean wiring via `set_deployment_manager()`

**`turn_manager.gd`** (light updates)
- Added `set_exhaustion_manager()` wiring
- Global turn counter advanced on `start_turn()`
- Automatic notification to `ExhaustionManager` after deployments

**New file: `exhaustion_manager_test.gd`**
- Comprehensive headless `SceneTree` tests covering ranking, comparison, never-exhausted players, and full `TurnManager` integration.

All code follows project conventions (detailed preloads, explicit typing, setter injection, excellent comments).

## How Exhaustion Order Works

- `PlayerState` detects when a player’s token pool hits zero and emits the `exhausted` signal.
- `TurnManager.perform_deployment()` calls into `ExhaustionManager.record_exhaustion_if_needed()`.
- `ExhaustionManager` assigns the next rank using its own `current_turn` counter and calls `PlayerState.mark_exhausted()`.
- Ranking rule: Lower rank number = exhausted earlier = wins ties (1 is best). Never-exhausted players get rank 999.
- `compare_exhaustion_priority(a, b)` returns the winner (or `""` on exact tie).

## Assumptions Made

- Exhaustion is primarily triggered via deployment actions in this narrow scope (card effects that remove the last unit can use the same `record_exhaustion()` API later).
- A simple global turn counter (incremented on `start_turn()`) is sufficient.
- Data lives in `PlayerState` (source of truth) while ordering/ranking coordination lives in the new `ExhaustionManager`.
- `TurnManager` is the natural integration point because it already has post-action hooks.

The system is minimal, fully integrated, and ready for War phase tiebreaker usage when that work begins.

---

*Implementation verified against the Exhaustion Order Design. All acceptance criteria met.*