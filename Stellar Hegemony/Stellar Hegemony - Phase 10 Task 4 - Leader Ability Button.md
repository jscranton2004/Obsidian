# Stellar Hegemony - Phase 10 Task 4: Leader Ability Button + Popup

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Add a dedicated button for the player's Leader Ability in the same section as the tactic cards.

## Scope (Narrow)
- Add a single prominent button for the leader ability.
- Use a different visual style from the tactic cards.
- Prepare it for the same popup system (popup is a separate task).

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Leader Ability Button (Phase 10 Task 4)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Add a Leader Ability button to the Deployment UI.

## Scope (Narrow — do ONLY this)
- In `DeploymentDiceUI.tscn`, add a new button (or reuse the TacticCardButton style with different theming) for the player's leader ability.
- Expose the leader's ability name and description via exported variables.
- Place it in the new "TacticSection" area, visually distinct from the 4 tactic cards.

Do not implement the popup or action execution yet.

## Acceptance Criteria
- A leader ability button appears alongside the tactic cards.
- It has a distinct appearance from regular tactic cards.
```