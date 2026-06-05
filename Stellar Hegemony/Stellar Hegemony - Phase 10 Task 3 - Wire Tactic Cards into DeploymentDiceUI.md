# Stellar Hegemony - Phase 10 Task 3: Wire Tactic Cards into DeploymentDiceUI

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Instantiate up to 4 `TacticCardButton` instances in the new section of `DeploymentDiceUI` and populate them with the player's chosen tactic cards.

## Scope (Narrow)
- Modify `DeploymentDiceUI.tscn` and its script to load the player's 4 tactic cards.
- Create instances of `TacticCardButton` and add them to the new section.
- No popup or action logic yet.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Wire Tactic Cards into DeploymentDiceUI (Phase 10 Task 3)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Display the player's 4 tactic cards in the DeploymentDiceUI.

## Scope (Narrow — do ONLY this)
- In `game/scenes/ui/DeploymentDiceUI.tscn` and `game/scripts/ui/deployment_dice_ui.gd`:
  - Load the 4 tactic cards the player selected during Leader Selection.
  - Instantiate `TacticCardButton` scenes and add them to the "TacticSection" container.
  - Set the `card_id` and `card_name` on each button.

Do not implement hover popups or "use card" logic yet.

## Acceptance Criteria
- When the Deployment screen loads, the player's 4 tactic cards appear as buttons in the new section.
- Each button shows the correct card name.
```