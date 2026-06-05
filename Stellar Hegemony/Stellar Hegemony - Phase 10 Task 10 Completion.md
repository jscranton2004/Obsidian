# Stellar Hegemony - Phase 10 Task 10 Completion

**Date:** 2026-06-05  
**Status:** Complete

## Summary
Replaced the full-screen modal overlay with viewport-aware panel positioning: top inset margin, horizontal center, and bottom clamping so the popup stays fully visible.

## Changes
- `game/scenes/ui/ActionDetailPopup.tscn` — removed dimmed `Background` ColorRect; panel fills a sized root control.
- `game/scripts/ui/action_detail_popup.gd`
  - `_attach_to_canvas_layer()` — reparent to `CanvasLayer` without `PRESET_FULL_RECT`.
  - `_fit_to_viewport()` — computes width/height from content, positions top at `top_margin` (48px default), centers horizontally, shifts up if needed to avoid bottom clip.
  - Root uses `MOUSE_FILTER_IGNORE`; only `Panel` blocks input (non-modal).
  - Refits on viewport resize and when unavailable text changes.

## Testing
1. Run **InGame** → Deployment Phase → hover a tactic card.
2. Popup top should sit below the screen top with clear margin; no clipping on sides or bottom.
3. Resize window — popup refits and stays on screen.
4. Trigger an unavailable message — popup grows/shrinks but stays in bounds.
5. **Cancel** and **Use This Action** still behave as in Tasks 8–9.

## Assumptions
- Default margins (48 top / 24 sides / 32 bottom) are sufficient for the HUD; tunable via exports on the scene.

*See also: [[Stellar Hegemony - Phase 10 Task 10 - Fix ActionDetailPopup Screen Fitting]]*