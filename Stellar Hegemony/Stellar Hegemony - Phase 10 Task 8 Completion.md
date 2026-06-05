# Stellar Hegemony - Phase 10 Task 8 Completion

**Date:** 2026-06-05  
**Status:** Complete

## Summary
Wired the Cancel button's `popup_closed` signal so `DeploymentDiceUI` dismisses the popup and returns control to tactic/leader selection.

## Changes
- `game/scripts/ui/deployment_dice_ui.gd`
  - Connect `popup.popup_closed` → `_close_current_popup` in `_show_tactic_popup()` and `_show_leader_popup()`.

## Testing
1. Enter Deployment Phase and hover a tactic card to open the popup.
2. Click **Cancel** — popup closes; no resources consumed.
3. Hover another tactic card — a new popup opens normally.
4. Repeat with the leader ability button.

## Assumptions
- `_close_current_popup()` already `queue_free`s the popup; no turn state changes on cancel.

*See also: [[Stellar Hegemony - Phase 10 Task 8 - Cancel Button Closes Popup and Restores Action Selection]]*