# Stellar Hegemony - Phase 10 Task 7: Center ActionDetailPopup on Screen

**Status:** Complete (2026-06-05)  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-04.md]] [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Move the existing ActionDetailPopup so it appears centered on the main game viewport instead of being positioned relative to the DeploymentDiceUI element.

## Scope (Narrow)
- Change only the positioning logic of ActionDetailPopup (or its parent container).
- Center it on the game screen / viewport.
- Remove any connection line.
- Do not change button behavior or any other systems.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 Task 7 - Center ActionDetailPopup on Game Screen

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under `C:\Obsidian Vault\Stellar-Hegemony` (Stellar Hegemony/ folder)  
**Current Date Context:** Stellar Hegemony - Handoff Note - 2026-06-04.md

## Goal
Move the existing ActionDetailPopup so it appears centered on the main game viewport instead of being positioned relative to the DeploymentDiceUI element.

## Scope (Narrow — do only this)
- Change only the positioning logic of ActionDetailPopup (or its parent container).
- Center it on the game screen / viewport.
- Keep any connection line removed.
- Do **not** change any button behavior, tactic execution, leader abilities, or UI styling.
- Do **not** touch any other files or systems.

## Current Known State
The popup currently appears attached to the dice element. The popup displays tactic name, description, "Use This Action", and "Cancel" buttons.

## Key References
- [[Stellar Hegemony - Handoff Note - 2026-06-04.md]]
- [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan.md]]
- [[Stellar Hegemony - Phase 10 Task 5 - Create reusable ActionDetailPopup]]

## Requirements
- Use Godot's built-in centering (anchor, pivot, or screen-size calculation) so the popup is always perfectly centered regardless of window size.
- Maintain the existing retro 1950s Jetson-style visual treatment.

## Assumptions
- The ActionDetailPopup scene/node already exists and is instantiated by the TacticCardButton / DeploymentDiceUI.
- No changes to the tactic data or execution logic are needed.

## Acceptance Criteria
- When mousing over a tactic card, the popup appears centered on the game screen.
- All other functionality remains unchanged.

Please implement this cleanly. After completion, briefly describe what was changed, how to test, and any assumptions.
```
