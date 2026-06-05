# Stellar Hegemony - Phase 10 Task 8: Cancel Button Closes Popup and Restores Action Selection

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-04.md]] [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Make the "Cancel" button in ActionDetailPopup close the popup and immediately return the player to the state where they can select a different tactic card or leader ability.

## Scope (Narrow)
- Implement Cancel button behavior only.
- The popup must close cleanly and return control to the action-selection layer.
- Do not consume resources or advance the turn.
- Do not change positioning or "Use This Action" behavior.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 Task 8 - Cancel Button Closes Popup and Restores Action Selection

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under `C:\Obsidian Vault\Stellar-Hegemony` (Stellar Hegemony/ folder)  
**Current Date Context:** Stellar Hegemony - Handoff Note - 2026-06-04.md

## Goal
Make the "Cancel" button in ActionDetailPopup close the popup and immediately return the player to the state where they can select a different tactic card or leader ability.

## Scope (Narrow — do only this)
- Implement Cancel button behavior only.
- The popup must close cleanly.
- Control must return to the DeploymentDiceUI / TacticCardButton layer so another action can be chosen.
- Do **not** consume any resources or advance the turn.
- Do **not** change positioning, "Use This Action" behavior, or any other UI.

## Current Known State
Cancel button exists but currently does not properly release control back to the action-selection layer.

## Key References
- [[Stellar Hegemony - Handoff Note - 2026-06-04.md]]
- [[Stellar Hegemony - Phase 10 Task 5 - Create reusable ActionDetailPopup]]
- [[Stellar Hegemony - Phase 10 Task 2 - Create TacticCardButton component]]

## Requirements
- Cancel must fully dismiss the popup and re-enable the tactic/leader buttons.
- Maintain exact mechanical fidelity — cancelling an action must be a no-op with zero side effects.

## Assumptions
- The popup is shown modally over the deployment UI.

## Acceptance Criteria
- Clicking Cancel closes the popup.
- Player can immediately mouse over another tactic card and open a new popup.
- No turn state or resources are altered.

Please implement this cleanly. After completion, briefly describe what was changed, how to test, and any assumptions.
```
