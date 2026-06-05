# Stellar Hegemony - Phase 10 Task 9: Add Precondition Check and Unavailable Feedback

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Handoff Note - 2026-06-04.md]] [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Before executing a tactic action, check whether it is currently possible. If not possible, show clear feedback instead of attempting the action.

## Scope (Narrow)
- Add a precondition check for the chosen tactic.
- If the action is invalid, display clear feedback.
- "Use This Action" should either execute or show the unavailable message.
- Do not implement actual tactic effects or change Cancel behavior.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 Task 9 - Add Precondition Check + Unavailable Feedback for Tactic Actions

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under `C:\Obsidian Vault\Stellar-Hegemony` (Stellar Hegemony/ folder)  
**Current Date Context:** Stellar Hegemony - Handoff Note - 2026-06-04.md

## Goal
Before executing a tactic action, check whether it is currently possible. If not possible, show clear feedback instead of attempting the action.

## Scope (Narrow — do only this)
- Add a precondition check for the chosen tactic (Expel, False Flag, etc.).
- If the action is invalid in the current game state, display feedback (e.g. a temporary message or disabled state).
- "Use This Action" button should either execute or show the unavailable message.
- Do **not** implement the actual tactic effects themselves (those are handled elsewhere).
- Do **not** change Cancel behavior or popup positioning.

## Current Known State
Tactic cards are displayed and the "Use This Action" button exists, but there is currently no validation that the chosen tactic can actually be performed.

## Key References
- [[Stellar Hegemony - Handoff Note - 2026-06-04.md]]
- [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan.md]]
- Tactic definitions in the codebase (Insurrection, Expel, Seize, False Flag, etc.)

## Requirements
- Use the existing TacticManager / game state to determine validity.
- Feedback must be clear and non-intrusive (toast, label on the popup, or similar retro-style message).
- Exact mechanical fidelity to Rumble Nation rules must be preserved.

## Assumptions
- Each tactic already has (or will have) a clear "is this action possible right now?" check.

## Acceptance Criteria
- When the action is possible → "Use This Action" executes normally.
- When the action is impossible → player sees clear feedback that the action is unavailable.
- No invalid actions are ever executed.

Please implement this cleanly. After completion, briefly describe what was changed, how to test, and any assumptions.
```
