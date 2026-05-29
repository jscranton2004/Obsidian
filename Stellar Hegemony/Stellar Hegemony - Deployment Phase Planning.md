# Stellar Hegemony - Deployment Phase Planning

**Status:** Planning / Definition  
**Date:** 2026-05-29  
**Purpose:** Define the full deployment phase rules before implementing placement logic.

## Overview
After leader selection, players enter the **Deployment Phase**. Each player rolls 3 dice. They choose which 2 dice determine the target zone and the remaining die determines how many units they must place.

## Dice Rules

### Zone Selection
- Player chooses **any two** of the three dice.
- The sum of those two dice determines the target sector (using the pre-assigned 2–12 zone values).

### Unit Quantity
The remaining (unselected) die determines how many units the player **must** place using this mapping:

| Die Result | Units to Place |
|------------|----------------|
| 1–2        | 1 unit         |
| 3–4        | 2 units        |
| 5–6        | 3 units        |

### Token Pools (per player)
- **1 Leader / Flag Ship token**
- **18 Fleet tokens**

Total starting units per player = 19.

## Placement Rules

- The player must place the exact number of units dictated by the die (or as many as remain in their pool, whichever is lower).
- The player may choose to place their **Flag Ship** as one of the units being placed in that deployment.
- A player may only ever have **one** Flag Ship on the map.
- If a player has no tokens left when it is their turn to deploy, they skip deployment.

### Special Low-Token Rules
- If the pool has only **1 token** remaining and the die calls for 3 units, only 1 token is placed.
- If the pool has **1 Fleet + 1 Leader** and the die calls for 3 units, the player must place both the Leader and the last Fleet (total 2 units).

## Ability Lockout
Once a player has placed their **last token**, they can no longer use:
- Their Leader card ability
- Any Tactic card abilities

## Tie-Breaker System (Exhaustion Order)

The order in which players run out of tokens determines tie resolution during the War phase:

| Order Player Runs Out | Tiebreaker Advantage                          |
|-----------------------|-----------------------------------------------|
| 1st                   | Wins all ties against every other player      |
| 2nd                   | Wins all ties except against the 1st player   |
| 3rd                   | Wins all ties against the 4th player only     |
| 4th (last)            | Loses all ties                                |

This order is determined at the moment each player places their final token.

## Scope Notes for Implementation

This planning note focuses on the **deployment phase logic** only. The following are intentionally excluded from this scope:

- War phase combat resolution
- Tactic / Leader card effect implementation
- Full player resource tracking UI
- End-of-game scoring using the 2–12 zone values

## References
- Core Mechanics: Split-dice deployment (2 for zone, 1 for quantity)
- Dice Deployment UI: Already emits `dice_selection_confirmed(sector_sum, unit_value)`
- Unit Representation Planning: Fleets and Flag Ships both count as units

---

*This document exists to prevent ambiguity when implementing the deployment system.*