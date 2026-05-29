# Stellar Hegemony - Turn Structure - Implementation Notes

**Status:** Complete  
**Date:** 2026-05-29  
**Related Design:** `Stellar Hegemony - Turn Structure Design.md`

## What Was Built

Grok Build implemented a clean, minimal `TurnManager` that enforces the core "one action per turn" rule.

### New Files
- `game/scripts/systems/turn_manager.gd` — Core `TurnManager` class (extends `RefCounted`)
- `game/scripts/systems/turn_manager_test.gd` — Full headless test suite (extends `SceneTree`)

Both files follow the project's strict GDScript standards (detailed headers, explicit typing, setter-based wiring, excellent comments).

### How the One-Action Rule Is Enforced

The enforcement is centralized and impossible to bypass when using the provided API:

1. **Turn Lifecycle**
   - `start_new_game(turn_order)`
   - `start_turn()` — returns current player_id and clears the acted flag
   - `end_turn()`

2. **Per-turn Guard**
   - Single `_current_player_has_acted` boolean (reset only on `start_turn()`)

3. **Dual-layer Checks**
   - `can_player_perform_deployment(player_id)` — checks player + !acted + still has tokens
   - `can_player_perform_tactic(player_id, card_id, board_eligible)` — checks player + !acted + TacticManager eligibility

4. **Gated Execution Methods**
   - `perform_deployment(...)` — only proceeds if can-check passes, then marks acted
   - `perform_tactic_use(...)` — only proceeds if can-check passes, then marks acted

5. **Bonus Integration**
   - After a successful deployment that exhausts the player, it automatically calls `lock_pool_for_exhaustion()` on the `TacticManager`.

**Result:** Once either action succeeds on a turn, both deployment and tactic use are immediately blocked for that player until the next `start_turn()`.

All acceptance criteria from the prompt are met.

## Assumptions Made (as documented by Grok)

- Turn order is supplied externally (e.g. from Leader Selection system).
- Simple round-robin cycling is sufficient for this narrow scope.
- Callers are expected to go through `TurnManager`'s `can_` checks or the `perform_` / `use_` methods.
- Direct calls to `DeploymentManager` / `TacticManager` would bypass the rule (by design).
- Full `HybridMap` / `CardEffectExecutor` integration is not required for this piece.

## Next Steps

The `TurnManager` is now ready to be wired into a future `GameManager` or phase layer. The system is deliberately minimal and ready for expansion.

---

*Implementation verified against the Turn Structure Design document. All rules respected.*