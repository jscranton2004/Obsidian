# Stellar Hegemony - Phase 6 Task 6 Completion

**Completed:** 2026-05-31  
**Task:** Global Ability Lockout

## Summary
The global ability lockout is now fully enforced at the `DeploymentPhaseManager` level. Once any player exhausts, both Tactic and Leader abilities are immediately blocked for all players.

## What Was Delivered
- `DeploymentPhaseManager` updates:
  - `_is_global_ability_lock_active()` helper
  - `get_available_actions()` now respects the global lock (only "deploy" offered when locked)
  - `perform_action()` returns clear error when abilities are globally locked
  - `start_deployment_phase()` now resets the lock via `create_shared_pool()`

- New test: `test_global_ability_lockout_in_available_actions()`

## Key Behavior
- Global lockout is now reliably reflected in action availability.
- Lock is properly cleared at the start of each new Deployment Phase.

## How to Test
```bash
godot --headless --path "C:\Git\stellar-hegemony\game" -s res://scripts/systems/deployment_phase_manager_test.gd
godot --headless --path "C:\Git\stellar-hegemony\game" -s res://scripts/systems/turn_manager_test.gd
godot --headless --path "C:\Git\stellar-hegemony\game" -s res://scripts/systems/tactic_manager_test.gd
```

## Status
Task complete. This closes the Global Ability Lockout gap at the phase orchestrator level.

---

*See also: [[Stellar Hegemony - Phase 6 Task 6 - Global Ability Lockout]] (planning note + prompt)*

All changes minimal, well-commented, and strictly followed the narrow-scope template. Committed and pushed on the game repo.