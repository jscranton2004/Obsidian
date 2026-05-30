# Stellar Hegemony - Phase 6 Task 1 Completion

**Completed:** 2026-05-30  
**Task:** One Action Per Turn Enforcement

## Summary
The core "one action per turn" rule has been successfully enforced in the `TurnManager`.

## What Was Delivered
- Added `_current_player_has_acted` state tracking
- Created gated methods:
  - `can_player_perform_deployment()`
  - `can_player_perform_tactic()`
  - `can_player_perform_leader()`
- Enforced mutual exclusivity between deployment and ability use on the same turn
- Added explicit exhaustion checks for Tactic and Leader abilities

## Key Behavior
- Once a player performs either deployment or an ability, the other category is blocked for the rest of the turn.
- Tactic and Leader abilities are now properly blocked after a player exhausts.

## Status
Task complete. This forms the foundation for Tactic/Leader integration and a proper Deployment Phase structure.