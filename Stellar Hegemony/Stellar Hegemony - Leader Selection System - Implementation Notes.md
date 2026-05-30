# Stellar Hegemony - Leader Selection System - Implementation Notes

**Status:** Complete  
**Date:** 2026-05-29  
**Related Design:** `Stellar Hegemony - Leader Selection System Design.md`

## What Was Built

The Leader Selection System was already present in the codebase and matches the specification exactly.

### Files
- `game/scripts/systems/leader_selection.gd` — Core `LeaderSelection` class
- `game/scripts/systems/leader_selection_test.gd` — Headless `SceneTree` test suite

### Key Features Implemented

- **Exact 6 leaders** with the canonical names and titles from the design docs.
- `start_new_game(num_players: int)` — main entry point.
- Correct pool size logic (`num_players + 1`, with 1 always excluded at 4 players).
- Random turn order + reverse picking order (last player in normal order picks first).
- `pick_leader(player_index, leader_id)` with full enforcement.
- Rich query API:
  - `get_offered_leaders()`
  - `get_turn_order()`
  - `get_picking_order()`
  - `get_available_leaders()`
  - `get_next_player_to_pick()`
  - `get_leader_for_player()`
  - `is_selection_complete()`
  - `get_state_summary()`
- `auto_assign_for_testing()` helper for full end-to-end simulation without UI.

### Polish Applied
- Fixed `%` array formatting in test output to satisfy the project’s strict “treat warnings as errors” rule.
- All tests pass cleanly under `godot --headless`.

## How to Test

```bash
godot --headless --path . -s "res://scripts/systems/leader_selection_test.gd"
```

Expected behaviour:
- Correct number of leaders offered for 2/3/4 players.
- Reverse picking order is always respected.
- All leaders in a pool are unique.
- Multiple runs produce different results.
- All internal assertions pass.

## Assumptions Made

- Player identity uses simple integer indices (0-based) for narrow-scope purity.
- Turn order is fully random every game.
- The 6 leaders are the canonical list from `Adapted Flag Ship Cards.md`.
- No integration with `PlayerState`, `TurnManager`, or leader abilities yet (per narrow-scope instruction).
- The `auto_assign_for_testing()` helper is the intended way to exercise full flow without UI.

## Next Integration

This system is ready to be wired into a future `GameManager` or setup flow once the broader game-start sequence is built.

---

*Implementation was already complete and fully compliant. Documentation added for traceability.*