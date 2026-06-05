# Stellar Hegemony - Phase 10 Task 10: Fix ActionDetailPopup Screen Fitting

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-04.md]] [[Stellar Hegemony - Phase 10 Tasks 7-9 Session Completion.md]]

## Goal
Adjust the ActionDetailPopup so it fits properly on screen — specifically, the top of the popup should be anchored below the top edge of the game screen with some margin, and the entire popup should remain fully visible within the viewport bounds.

## Scope (Narrow)
- Adjust anchoring/positioning of ActionDetailPopup so its top edge has breathing room from the top of the screen.
- Ensure the popup is fully visible and not clipped or offset awkwardly.
- Keep it independent of the DeploymentDiceUI layout.
- Do not add a full-screen backdrop or turn it into a modal overlay.
- Do not change button logic, precondition checks, or tactic execution.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 Task 10 - Fix ActionDetailPopup Screen Fitting

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under `C:\Obsidian Vault\Stellar-Hegemony` (Stellar Hegemony/ folder)  
**Current Date Context:** Stellar Hegemony - Handoff Note - 2026-06-05.md + screenshots showing current offset popup

## Goal
Adjust the ActionDetailPopup so it fits properly on screen — specifically, the top of the popup should be anchored below the top edge of the game screen with some margin, and the entire popup should remain fully visible within the viewport bounds.

## Scope (Narrow — do only this)
- Adjust anchoring/positioning of ActionDetailPopup so its top edge has breathing room from the top of the screen.
- Ensure the popup is fully visible and not clipped or offset awkwardly.
- Keep it independent of the DeploymentDiceUI layout.
- Do **not** add a full-screen backdrop or turn it into a modal overlay.
- Do **not** change any button logic, precondition checks, tactic execution, or Cancel behavior.

## Current Known State
After Task 7 the popup still appears offset and partially clipped relative to the DeploymentDiceUI panel (as shown in the attached screenshots). It is not staying fully visible on screen.

## Key References
- [[Stellar Hegemony - Handoff Note - 2026-06-05.md]]
- [[Stellar Hegemony - Phase 10 Task 7 - Center ActionDetailPopup on Screen]]
- [[Stellar Hegemony - Phase 10 Tasks 7-9 Session Completion.md]]

## Requirements
- The top of the popup should be inset from the top edge of the game screen.
- The entire popup must remain fully visible within the viewport.
- The popup must not be affected by the layout or anchors of DeploymentDiceUI.
- Maintain the existing retro 1950s Jetson-style visual treatment.

## Assumptions
- Minor adjustments to anchors, margins, or position calculation will be sufficient.

## Acceptance Criteria
- When hovering a tactic card, the ActionDetailPopup appears fully on screen with its top edge below the top of the game screen.
- The popup is no longer offset or clipped.
- All existing functionality (Cancel, Use This Action, precondition feedback) continues to work.

Please implement this cleanly. After completion, briefly describe what was changed, how to test, and any assumptions.
```
