# Stellar Hegemony - Phase 10 Task 10: Fix ActionDetailPopup Modal Centering and Backdrop

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-04.md]] [[Stellar Hegemony - Phase 10 Tasks 7-9 Session Completion.md]]

## Goal
Make the ActionDetailPopup behave as a true full-screen modal that is always centered on the game viewport with a dimmed backdrop, completely independent of the DeploymentDiceUI layout.

## Scope (Narrow)
- Force reparenting of ActionDetailPopup to the top-level CanvasLayer (or InGame) on show.
- Set full-rect anchors + center pivot so the popup is always perfectly centered.
- Add a simple dimmed ColorRect backdrop behind the popup content.
- Ensure the popup renders above all other UI elements.
- Do not change button logic, precondition checks, or tactic execution.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 Task 10 - Fix ActionDetailPopup Modal Centering and Backdrop

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under `C:\Obsidian Vault\Stellar-Hegemony` (Stellar Hegemony/ folder)  
**Current Date Context:** Stellar Hegemony - Handoff Note - 2026-06-05.md + screenshots showing current offset popup

## Goal
Make the ActionDetailPopup behave as a true full-screen modal that is always centered on the game viewport with a dimmed backdrop, completely independent of the DeploymentDiceUI layout.

## Scope (Narrow — do only this)
- Force reparenting of ActionDetailPopup to the top-level CanvasLayer (or InGame) when shown.
- Set full-rect anchors + center pivot so the popup content is always perfectly centered on screen.
- Add a dimmed ColorRect backdrop behind the popup content.
- Ensure the popup renders above all other UI elements.
- Do **not** change any button logic, precondition checks, tactic execution, or Cancel behavior.

## Current Known State
After Task 7 the popup still appears offset and partially clipped relative to the DeploymentDiceUI panel (as shown in the attached screenshots). It is not behaving as a proper centered modal.

## Key References
- [[Stellar Hegemony - Handoff Note - 2026-06-05.md]]
- [[Stellar Hegemony - Phase 10 Task 7 - Center ActionDetailPopup on Screen]]
- [[Stellar Hegemony - Phase 10 Tasks 7-9 Session Completion.md]]

## Requirements
- The popup must appear centered on the full game viewport.
- A semi-transparent dark backdrop should appear behind the popup content.
- The popup must not be affected by the layout or anchors of DeploymentDiceUI.
- Maintain the existing retro 1950s Jetson-style visual treatment.

## Assumptions
- There is a top-level CanvasLayer or Control that can serve as the reparent target.

## Acceptance Criteria
- When hovering a tactic card, the ActionDetailPopup appears perfectly centered on screen with a dimmed backdrop.
- The popup is no longer offset or clipped by the dice panel.
- All existing functionality (Cancel, Use This Action, precondition feedback) continues to work.

Please implement this cleanly. After completion, briefly describe what was changed, how to test, and any assumptions.
```
