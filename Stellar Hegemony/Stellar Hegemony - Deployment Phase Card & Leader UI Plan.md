# Stellar Hegemony - Deployment Phase Card & Leader UI Plan

**Status:** Planning  
**Related:** [[Stellar Hegemony - Deployment Phase Planning]], [[Stellar Hegemony - Tactic Card System Planning]], [[Stellar Hegemony - Phase 6 Task 2 - Tactic Card Integration]]

## Overview
We need to add UI support for using **Tactic Cards** and **Leader Abilities** during the Deployment Phase. Currently only dice deployment is available. Players should be able to choose one action per turn (dice OR card OR leader ability).

The user suggested extending `DeploymentDiceUI.tscn` vertically and adding a card/ability sub-component with mouse-over popups.

## Existing Foundations (already implemented)
- `TacticManager` — full logic for the 12 tactic cards, eligibility checks, one-use-per-game rule, global lockout.
- `DeploymentPhaseManager` — high-level orchestration that already references Deploy / Tactic / Leader choices.
- `TurnManager` — enforces the "one action per turn" rule (tested).
- Leader ability gating exists in tests.
- Card data and descriptions exist in `tactic_manager.gd`.

## Proposed Breakdown (Narrow-Scope Tasks)

### Task 1: Extend DeploymentDiceUI Scene
- Make the panel taller (increase Y size of the main container).
- Add a new section below the dice UI for "Tactic Cards & Leader Ability".
- Create placeholder slots for up to 4 tactic cards + 1 leader ability.

### Task 2: Create TacticCardButton Component
- New reusable scene + script (`TacticCardButton.tscn` / `.gd`).
- Displays card name + small icon.
- On mouse hover → show a centered popup with full description + "Use This Card" button.
- Button is only enabled if the player can legally use it this turn.

### Task 3: Wire Tactic Cards into DeploymentDiceUI
- Load the player's 4 chosen tactic cards.
- Instantiate `TacticCardButton` instances in the new section.
- On "Use This Card" → call into `DeploymentPhaseManager` / `TacticManager` and consume the action.

### Task 4: Leader Ability Button + Popup
- Similar component for the player's leader ability (different visual treatment).
- Reuse or adapt the same popup system.
- Enforce the one-action-per-turn rule.

### Task 5: Popup System (Reusable)
- Create a generic `ActionDetailPopup.tscn` that can be reused for both tactics and leader abilities.
- Centered on screen, shows title + full text + action button.
- Handles closing and action confirmation.

### Task 6: Integration & Testing
- Connect everything through `DeploymentPhaseManager`.
- Ensure only one action can be taken per turn.
- Test flow: dice deployment vs card vs leader ability.

## Next Step
Once approved, we will create individual narrow-scope planning notes + ready-to-use Grok Build prompts for each task above, starting with Task 1 (scene extension).

*This keeps us in the narrow-scope discipline while delivering a complete feature.*