# Stellar Hegemony - Tactic and Leader Card Effects Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define how the actual effects of Tactic Cards and Leader Cards will be implemented.

## Overview
Both Tactic Cards and Leader (Flag Ship) Cards provide powerful one-time effects. Each player is limited to using only **one** of each type per game. Effects must integrate cleanly with the existing zone, unit, and deployment systems.

## Core Principles

- Effects are **one-time use** per card (already enforced by `TacticManager` and `LeaderSelection`).
- Effects must respect the current **unit representation** model (Fleets + Flag Ships as units in zones).
- Effects must work with the existing definition of **"adjacent"** (hyperspace or wormhole) and the distinction between movement types.
- Once any player runs out of units, **all** Tactic and Leader card usage is locked out globally.

## Required Systems Interaction

### Zones (`zone.gd`)
- Effects will frequently need to:
  - Move units between zones
  - Add/remove units from a zone
  - Check ownership of units in a zone
  - Replace enemy units

### HybridMap
- Will need helper methods such as:
  - `get_zones_adjacent_to(zone)`
  - `get_zones_connected_by_wormhole(zone)`
  - `get_zones_connected_by_hyperspace(zone)`
  - `get_player_units_in_zone(player, zone)` (fleets + flagship count)

### Reserves
- Several cards interact with "reserves".
- We need a per-player reserves system (currently not implemented).

### DeploymentManager
- Some effects (e.g. Reinforce) are essentially a special form of deployment.
- Effects should be able to call into deployment logic where appropriate.

## Tactic Card Effects Summary

### Movement Cards
- **Scout** — Move 1 fleet to an adjacent system.
- **Hyperspace Invasion** — Move 2 fleets via hyperspace only.
- **Wormhole Invasion** — Move 2 fleets via wormhole only.
- **Sub-Light Squadron** — Move half (rounded down) of fleets from one system to an adjacent system.
- **Shadow Fleet** — Move 1 fleet to any system where the player already has fleets (special movement).
- **Converge on the Core** — Move any number of fleets to the Core from adjacent systems.

### Support & Disruption Cards
- **Reinforce** — Deploy 1 fleet from reserves into a system where the player already has fleets.
- **Insurrection** — Replace 1 enemy fleet with one from reserves.
- **Expel** — Move 1 enemy fleet from a system where you have fleets to an adjacent system.
- **Seize** — Move 1 enemy fleet to a system where you have fleets.
- **False Flag** — Move 1 of your fleets + 2 enemy fleets together to an adjacent system.
- **Emergency Withdrawal** — Return 2 of your fleets from any system(s) to reserves.

## Leader Card Effects Summary

- **Commander Skitter** — Move up to 3 fleets via hyperspace from Flag Ship's location.
- **Admiral Vance "Ironjaw" Hale** — Move Flag Ship up to 2 systems (must have fleets in systems passed through). May bring 1 fleet along.
- **High Lord Glubthar** — Move up to 3 units (fleets or Flag Ship) via wormhole.
- **Sky Marshal Quill** — Place up to 3 fleets from reserves into systems adjacent to Flag Ship (max 1 per system).
- **Lord Granite** — Replace 1 enemy fleet in up to 2 adjacent systems with a fleet from reserves.
- **The Many** — Move up to 3 enemy fleets of the same opponent from Flag Ship's location to adjacent systems.

## Recommended Implementation Approach

### Option A (Preferred for clarity)
Create a `CardEffectExecutor` (or `EffectSystem`) that contains methods such as:
- `execute_tactic(card_id, player, context)`
- `execute_leader(leader_id, player, context)`

Each effect is implemented as a separate method or small class. The executor receives the current game state (zones, player units, reserves) and modifies it.

### Option B
Attach effect methods directly to `TacticManager` and a future `LeaderManager`.

### Context Object
A `CardExecutionContext` should be passed in containing:
- Current `HybridMap`
- Player unit data
- Reserves data
- Flag Ship locations

## Open Questions / Future Considerations

- How are "reserves" represented? (Simple integer count per player is likely sufficient for now.)
- How do we handle partial movement when a player has fewer units than the card allows?
- Should movement effects trigger visual feedback / animations?
- How do we handle the "must be able to perform the action" check for each card (this is currently the caller's responsibility)?

## References
- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - Adapted Flag Ship Cards.md`
- `Stellar Hegemony - Tactic Card System Planning.md`
- `Stellar Hegemony - Deployment Phase Planning.md`
- `Stellar Hegemony - Unit Representation Planning.md`

---

*This design document provides the foundation for implementing the actual card effects while staying consistent with existing systems.*