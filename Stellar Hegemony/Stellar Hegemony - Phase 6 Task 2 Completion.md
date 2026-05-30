# Stellar Hegemony - Phase 6 Task 2 Completion

**Completed:** 2026-05-30  
**Task:** Tactic Card Integration

## Summary
Tactic cards have been successfully integrated into the turn system. Using a Tactic now counts as a player's action for the turn and respects all exhaustion and one-use rules.

## What Was Delivered
- `TacticManager` wired into `TurnManager`
- Tactic usage now gated behind `can_player_perform_tactic()`
- One Tactic per game enforcement active
- Tactic usage blocked after player exhaustion and after global exhaustion

## Key Behavior
- Players can now choose to either deploy units **or** use a Tactic on their turn (but not both)
- Tactic usage is properly blocked once any player has exhausted

## Status
Task complete. This continues the foundation laid by Task 1 and prepares the ground for Leader Ability Integration.

---

*See also: [[Stellar Hegemony - Phase 6 Task 2 - Tactic Card Integration]] (planning note)*