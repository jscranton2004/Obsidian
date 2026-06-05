# Stellar Hegemony - Phase 10 Task 1: Extend DeploymentDiceUI Scene

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Extend the `DeploymentDiceUI.tscn` panel vertically so there is space for a new "Tactic Cards & Leader Ability" section below the existing dice controls.

## Scope (Narrow)
- Increase the vertical size of the main container/panel in `DeploymentDiceUI.tscn`.
- Add a new `VBoxContainer` or section placeholder labeled "Tactic Cards & Leader Ability".
- Do not add any buttons, logic, or card instances yet.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Extend DeploymentDiceUI Scene (Phase 10 Task 1)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Make `DeploymentDiceUI.tscn` taller so we can later add a Tactic Cards & Leader Ability section.

## Scope (Narrow — do ONLY this)
- Open `game/scenes/ui/DeploymentDiceUI.tscn`
- Increase the vertical size of the root panel/container (suggested: add ~300–400 pixels of extra height).
- Add a new `VBoxContainer` (or similar) below the existing dice elements, named "TacticSection" or "CardLeaderSection".
- Add a simple `Label` inside it with the text "Tactic Cards & Leader Ability" as a placeholder.

Do not add any buttons, scripts, or card logic yet.

## Acceptance Criteria
- The scene is visibly taller when opened in the editor.
- A new section exists below the dice UI with a placeholder label.
- No other changes to the scene or any scripts.

Please make this small scene extension.
```