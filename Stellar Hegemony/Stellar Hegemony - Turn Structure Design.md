# Stellar Hegemony - Turn Structure Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define the turn structure and action choice rules for the game.

## Overview
After leader selection and during the Deployment Phase, players take turns. On each turn, a player must choose **one** of two mutually exclusive actions:
1. Roll dice to deploy units, **or**
2. Use one available Tactic Card (if eligible)

## Core Rules

### Action Choice
- A player may perform **only one** action per turn.
- The two actions are mutually exclusive.
- Using a Tactic Card ends the turn (no deployment on the same turn).
- Rolling dice to deploy ends the turn (no tactic use on the same turn).

### Eligibility
- A player may only use a Tactic Card if:
  - They have not yet used their one allowed Tactic Card this game
  - They are currently able to perform the action on the card
  - The global lockout has not been triggered (any player has run out of units)

### Turn Order
- Turn order is determined at the start of the game (via the Leader Selection system).
- The player who goes last in turn order picks their leader first.
- Normal play proceeds in the established turn order.

### End of Turn
- After a player completes their chosen action, their turn ends.
- Play passes to the next player in turn order.

## Scope for Initial Implementation

- Focus on enforcing the "one action per turn" rule.
- Support the two action types (Deploy vs Use Tactic).
- Do **not** implement full phase transitions or War phase yet.
- Keep changes minimal and build on existing managers (`DeploymentManager`, `TacticManager`, `PlayerState`).

## References
- `Stellar Hegemony - Deployment Phase Planning.md`
- `Stellar Hegemony - Tactic Card System Planning.md`
- `Stellar Hegemony - Integration & Stabilization Design.md`

---

*This system enforces the core "one action per turn" gameplay rule.*