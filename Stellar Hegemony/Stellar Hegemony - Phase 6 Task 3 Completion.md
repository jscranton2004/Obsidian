# Stellar Hegemony - Phase 6 Task 3 Completion

**Completed:** 2026-05-31  
**Task:** Leader Ability Integration

## Summary
Leader abilities have been successfully integrated into the turn system. Using a Leader ability now counts as a player's action for the turn and respects all exhaustion and one-use rules, exactly mirroring the Tactic Card Integration from Task 2.

## What Was Delivered
- `perform_leader_use()` now calls `_maybe_lock_abilities_for_exhaustion()` (symmetric to Tactic and Deployment paths).
- Renamed helper: `_maybe_lock_tactics_for_exhaustion()` → `_maybe_lock_abilities_for_exhaustion()` (handles global lock for both Tactic cards and Leader abilities via `TacticManager`).
- Documentation & comments updated in `turn_manager.gd` with explicit Phase 6 Task 3 references and cross-references to the Task 2 template.
- Minor test comment added.

No new effects, no UI changes, no changes to `PlayerState` or `CardEffectExecutor` — pure integration work.

## Key Behavior
- Players can now choose to either deploy units, use a Tactic, **or** use a Leader ability on their turn (but only one).
- Leader usage is properly blocked once any player has exhausted (global lockout).
- One Leader ability per game enforcement remains in place.

## How to Test
Run the headless test:
```
godot --headless --path "C:\Git\stellar-hegemony\game" -s res://scripts/systems/turn_manager_test.gd
```

Key passing tests:
- Test 7: Leader participates in one-action rule.
- Test 8: Exhausted players blocked from Leader abilities.

Manual verification also possible by wiring `TurnManager` + `DeploymentManager` + `TacticManager` and confirming the action gating and global lockout.

## Status
Task complete. This continues the foundation laid by Tasks 1 and 2.

---

*See also: [[Stellar Hegemony - Phase 6 Task 3 - Leader Ability Integration]] (planning note + prompt)*

All changes minimal, well-commented, and strictly followed the narrow-scope template. Committed and pushed on the game repo.