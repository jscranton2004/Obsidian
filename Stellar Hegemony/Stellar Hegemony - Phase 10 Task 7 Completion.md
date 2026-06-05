# Stellar Hegemony - Phase 10 Task 7 Completion

**Date:** 2026-06-05  
**Status:** Complete

## Summary
Centered `ActionDetailPopup` on the main game viewport by reparenting it to the parent `CanvasLayer` and applying a full-rect anchor preset on show.

## Changes
- `game/scripts/ui/action_detail_popup.gd`
  - Added `_attach_as_screen_overlay()` — reparents popup to the nearest `CanvasLayer`, sets `PRESET_FULL_RECT`, raises `z_index`, and calls `move_to_front()`.
  - Added `_find_parent_canvas_layer()` helper.

## Testing
1. Run the game and enter Deployment Phase.
2. Mouse over a tactic card — popup should appear centered on the full screen with dimmed backdrop.
3. Resize the window — popup panel stays centered.
4. Confirm dice/tactic buttons still work as before (no button-behavior changes in this task).

## Assumptions
- Popup is instantiated under `DeploymentDiceUI`, which lives under `CanvasLayer` in `InGame.tscn`.
- No connection line existed in code; none added.

*See also: [[Stellar Hegemony - Phase 10 Task 7 - Center ActionDetailPopup on Screen]]*