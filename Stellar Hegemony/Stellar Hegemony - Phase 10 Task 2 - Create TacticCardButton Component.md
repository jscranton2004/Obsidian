# Stellar Hegemony - Phase 10 Task 2: Create TacticCardButton Component

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Create a reusable `TacticCardButton` scene that displays a tactic card name and handles mouse hover to show a detail popup.

## Scope (Narrow)
- Create new files: `scenes/ui/TacticCardButton.tscn` and `scripts/ui/tactic_card_button.gd`.
- The button should show the card name.
- On mouse hover, it should eventually trigger a popup (popup creation is a later task).

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Create TacticCardButton Component (Phase 10 Task 2)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Create a reusable button component for tactic cards.

## Scope (Narrow — do ONLY this)
- Create `game/scenes/ui/TacticCardButton.tscn`
- Create `game/scripts/ui/tactic_card_button.gd`
- The scene should contain a `Button` (or `TextureButton`) that displays the card name.
- Expose an exported variable `card_id: String` and `card_name: String`.
- Add basic hover detection (signal or function) — the actual popup will be wired in a later task.

Do not implement the full popup yet.

## Acceptance Criteria
- The component can be instantiated and shows a card name.
- It has the basic structure for future hover + popup behaviour.
- No integration with `DeploymentDiceUI` yet.
```