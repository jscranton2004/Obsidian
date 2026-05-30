# Stellar Hegemony - Phase 6 Task 2: Tactic Card Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]]

## Goal
Integrate Tactic cards into the turn structure so they can be used as one of the two mutually exclusive actions per turn during the Deployment Phase.

## Scope (Narrow)
- Wire the existing `TacticManager` into the `TurnManager` so Tactic usage respects the "one action per turn" rule.
- Enforce the "one Tactic per game" limitation.
- Respect the global ability lockout when any player has exhausted.

## Why This Task
Tactic cards are a core part of the original Rumble Nation rules. With the "one action per turn" enforcement now in place, we can properly integrate Tactic usage as a valid alternative to deployment on a player's turn.