# Stellar Hegemony - Reserves System Design (Revised)

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define the correct Reserves model using a single 18-unit fleet pool.

## Overview

Each player has a **single pool of 18 fleets**. Reserves represent the portion of those 18 fleets that are **not currently deployed** on the board.

## Core Rules

### Single Pool Model
- Total fleets per player = **18**
- `reserves` = fleets not on the board
- `deployed` = fleets currently on the board
- `reserves + deployed = 18` at all times (until losses occur)

### How Reserves Work
- Players start the game with **18 fleets in reserves**.
- Deploying a fleet moves it from reserves → board.
- Returning a fleet to reserves (via Emergency Withdrawal, etc.) moves it from board → reserves.
- Exhaustion only triggers when **total fleets = 0** (reserves + deployed = 0).

### Card Interactions
- **Reinforce**: Move 1 fleet from reserves to a system the player already occupies.
- **Insurrection**: Return 1 enemy fleet to its reserves, then move 1 of your fleets from reserves to that system.
- **Emergency Withdrawal**: Move up to 2 of your fleets from the board back to reserves.

## Scope for Implementation

- Track total fleets (18) and currently deployed fleets in `PlayerState`.
- Provide methods to move fleets between reserves and the board.
- Support the three cards listed above via `CardEffectExecutor`.
- Keep the implementation minimal.

## Integration Points

- `PlayerState` is the source of truth for fleet counts.
- `CardEffectExecutor` should use the new reserves methods.
- Exhaustion logic must check the **combined** total (not just deployed fleets).

## References

- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`

---

*This revised model treats reserves as the undeployed portion of the single 18-unit pool.*