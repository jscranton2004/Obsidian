# Stellar Hegemony - Phase 6 Task 1: One Action Per Turn Enforcement

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]]

## Goal
Enforce the core rule that a player may perform only **one** action per turn during the Deployment Phase: either roll dice to deploy units, or use one Tactic/Leader ability.

## Scope (Narrow)
- Extend the existing `TurnManager` to track and enforce the "one action per turn" rule.
- Prevent a player from both deploying and using a Tactic/Leader ability on the same turn.
- Block Tactic/Leader usage after a player has exhausted their units.

## Why This Task
This is the highest-priority remaining gap. Without proper turn enforcement, the Deployment Phase cannot function correctly, and Tactic/Leader card integration cannot be completed. This is a foundational rule from the original game.