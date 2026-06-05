# Stellar Hegemony - Phase 10 Master Chain Prompt

**Status:** Ready to use  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Purpose
This is a single master prompt that instructs Grok Build to complete all six Phase 10 tasks in order, while still respecting narrow-scope discipline.

## Master Chain Prompt for Grok Build

```
# Prompt for Grok Build: Phase 10 - Deployment Phase Card & Leader UI (Master Chain)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Overall Goal
Implement the full set of UI features that allow players to use Tactic Cards and Leader Abilities during the Deployment Phase. Complete the six tasks below **one at a time** in order. After finishing each task, briefly summarise what was delivered and then proceed to the next task.

## Tasks (Complete in this exact order)

### Task 1: Extend DeploymentDiceUI Scene
Follow the instructions in: Stellar Hegemony - Phase 10 Task 1 - Extend DeploymentDiceUI Scene.md

### Task 2: Create TacticCardButton Component
Follow the instructions in: Stellar Hegemony - Phase 10 Task 2 - Create TacticCardButton Component.md

### Task 3: Wire Tactic Cards into DeploymentDiceUI
Follow the instructions in: Stellar Hegemony - Phase 10 Task 3 - Wire Tactic Cards into DeploymentDiceUI.md

### Task 4: Leader Ability Button + Popup
Follow the instructions in: Stellar Hegemony - Phase 10 Task 4 - Leader Ability Button.md

### Task 5: Reusable Action Detail Popup
Follow the instructions in: Stellar Hegemony - Phase 10 Task 5 - Reusable Action Detail Popup.md

### Task 6: Integration & Testing
Follow the instructions in: Stellar Hegemony - Phase 10 Task 6 - Integration and Testing.md

## Rules for Grok Build
- Complete the tasks **strictly in order**.
- After each task, output a short summary of what was changed and any assumptions made.
- Only move on to the next task after completing the current one.
- Keep changes narrow-scope for each individual task.
- If any task cannot be completed cleanly, stop and report the blocker before continuing.

Begin with Task 1 now.
```