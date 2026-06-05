# Stellar Hegemony - Phase 10 Task 5: Reusable Action Detail Popup

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Create a reusable centered popup scene that displays the full text of a tactic card or leader ability, with a "Use" / "Select" button.

## Scope (Narrow)
- Create `ActionDetailPopup.tscn` and its script.
- The popup should accept a title and description and show a confirm button.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Reusable Action Detail Popup (Phase 10 Task 5)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Create a reusable popup for showing tactic/leader ability details.

## Scope (Narrow — do ONLY this)
- Create `game/scenes/ui/ActionDetailPopup.tscn`
- Create `game/scripts/ui/action_detail_popup.gd`
- The popup should:
  - Be centered on screen
  - Display a title and full description text
  - Have a "Use This Action" button
  - Emit a signal when the button is pressed (or closed)

Do not wire it to the tactic buttons yet.

## Acceptance Criteria
- The popup scene can be instantiated and displays title + description.
- It has a confirm button that can be connected later.
```