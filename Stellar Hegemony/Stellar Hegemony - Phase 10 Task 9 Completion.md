# Stellar Hegemony - Phase 10 Task 9 Completion

**Date:** 2026-06-05  
**Status:** Complete

## Summary
Added precondition validation before executing tactic or leader actions from `ActionDetailPopup`. Invalid actions show a retro-styled unavailable message on the popup instead of calling `perform_action`.

## Changes
- `game/scripts/ui/action_detail_popup.gd` + `ActionDetailPopup.tscn`
  - Added `UnavailableLabel` and `show_unavailable_message()` / `clear_unavailable_message()`.
- `game/scripts/ui/deployment_dice_ui.gd`
  - Validates via `TurnManager.can_player_perform_tactic/leader` and `CardEffectExecutor.can_player_perform_tactic` (board eligibility).
  - Shows specific unavailable reasons (turn, pool lock, already used, board state, etc.).
  - Passes computed `board_eligible` into `perform_action` on success.
- `game/scripts/levels/in_game.gd`
  - Wires `set_turn_manager()` and `set_human_player_id()` on `DeploymentDiceUI`.

## Testing
1. Start a game, open a tactic popup, click **Use This Action** when requirements are met → action executes as before.
2. With no movable fleets / no enemy targets, click **Use This Action** → red unavailable message appears; popup stays open; no card consumed.
3. After using your one tactic for the game, try another → unavailable message explains already used.
4. Cancel still works unchanged.

## Assumptions
- `TacticManager.build_execution_context()` is available (wired via `TurnManager.set_deployment_manager`).
- Leader board preconditions are not checked beyond `TurnManager` gates (leader effects not fully wired in UI demo).

*See also: [[Stellar Hegemony - Phase 10 Task 9 - Add Precondition Check and Unavailable Feedback]]*