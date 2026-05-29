# Stellar Hegemony - Reserves System Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define how the Reserves pool works and how it integrates with card effects and deployment.

## Overview

Reserves represent a secondary pool of units that players can move to and from during the game, primarily via Tactic Cards. This creates interesting tactical decisions around when to pull units back into reserves or deploy from them.

## Core Rules

### What Are Reserves?
- Every player starts with a number of units in **reserves** (exact starting count TBD, but separate from the initial deployment pool).
- Reserves are **not** part of the main token pool used for exhaustion tracking.
- Units in reserves can be deployed via specific cards (e.g. **Reinforce**).

### Key Interactions (from Adapted Tactic Cards)
- **Reinforce**: Deploy 1 FLEET from your reserves into any system where you already have FLEETS.
- **Insurrection**: Return 1 enemy FLEET to its reserves and replace it with a FLEET from your reserves.
- **Emergency Withdrawal**: Return 2 of your FLEETS from any system(s) to your reserves.

### Rules
- Units moved to reserves are removed from the board.
- Units deployed from reserves count as a normal deployment action (they are placed on the board).
- Reserves do **not** count toward a player’s exhaustion state (only the main fleet + flagship pool does).
- There is no limit to how many units can be in reserves at once.

## Scope for Initial Implementation

- Add a `reserves` counter to `PlayerState`.
- Provide methods to move units between the board and reserves.
- Support the three cards that directly reference reserves (`Reinforce`, `Insurrection`, `Emergency Withdrawal`).
- Keep changes minimal — do not implement full card execution yet if it is already handled by `CardEffectExecutor`.

## Integration Points

- `PlayerState` should own the `reserves` value.
- `CardEffectExecutor` should be able to read/write reserves when executing the relevant effects.
- `TurnManager` / action gating should treat deploying from reserves the same as normal deployment (one action per turn).

## References

- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`
- `Stellar Hegemony - Card Effect Executor - Implementation Notes.md`

---

*Reserves add meaningful tactical depth without complicating the core exhaustion or deployment systems.*