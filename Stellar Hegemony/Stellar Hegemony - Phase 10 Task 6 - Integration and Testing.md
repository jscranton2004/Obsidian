# Stellar Hegemony - Phase 10 Task 6: Integration & Testing

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Deployment Phase Card & Leader UI Plan]]

## Goal
Connect the new UI components to `DeploymentPhaseManager` and `TacticManager` so that selecting a card or leader ability counts as the player's one action for the turn.

## Scope (Narrow)
- Wire hover → popup → action selection.
- Enforce the one-action-per-turn rule.
- Basic testing of the flow.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Integration & Testing (Phase 10 Task 6)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game

## Goal
Make the new card/leader UI functional with the existing game systems.

## Scope (Narrow — do ONLY this)
- Connect `TacticCardButton` hover to open `ActionDetailPopup`.
- On "Use This Action", call the appropriate method on `TacticManager` / `DeploymentPhaseManager`.
- Ensure the UI respects the "one action per turn" rule from `TurnManager`.
- Add basic visual feedback when an action is taken.

## Acceptance Criteria
- Clicking "Use" on a tactic card or leader ability consumes the player's action for that turn.
- The UI updates correctly after an action is chosen.
- Dice deployment is disabled once a card/leader action is taken (and vice versa).
```