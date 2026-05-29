# Prompt for Grok Build: PlayerState Class

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Introduce a proper `PlayerState` class to manage per-player data (replacing scattered dictionaries).

## Key Reference Documents
- `Stellar Hegemony - Card Effect Executor - Implementation Notes.md`
- `Stellar Hegemony - Deployment Phase Planning.md`
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md`

## Requirements

### Scope (Narrow)
Create the foundational `PlayerState` class and basic integration. Do not implement full game loop or UI yet.

### PlayerState Responsibilities
The class should track:
- Player ID / Faction
- Remaining fleet tokens (starting at 18)
- Flag Ship status (whether it has been placed)
- Flag Ship current location (zone ID or null)
- Reserves count (starting at 0)
- Whether the player has used their Tactic Card
- Whether the player has used their Leader ability

### Core Methods
- `spend_fleets(amount)` — Reduce fleet count (with validation)
- `place_flagship(zone_id)` — Place the Flag Ship (only once)
- `move_flagship(to_zone_id)`
- `add_to_reserves(amount)`
- `remove_from_reserves(amount)`
- `has_flagship_placed()`
- `is_exhausted()` — Returns true when fleet count + flagship status reaches zero

### Integration Points
- Update `DeploymentManager` to use `PlayerState`
- Update `CardEffectExecutor` / `CardExecutionContext` to work with `PlayerState`
- `TacticManager` should be able to mark a player as having used their tactic

### Scope Boundaries
- Keep this focused on data + basic methods
- Do **not** implement full turn system or UI

## Acceptance Criteria

- `PlayerState` can accurately track fleets, reserves, and Flag Ship status
- Methods correctly prevent invalid states (e.g., spending more fleets than available)
- Other managers can be updated to use `PlayerState` with minimal friction

## Files You Will Likely Touch
- `game/scripts/systems/player_state.gd` (new)
- Minor updates to `deployment_manager.gd` and `card_effect_executor.gd`

## Important Notes
- This class will become central to future work (reserves, exhaustion order, tiebreakers)
- Keep the API clean and well-documented

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How `PlayerState` integrates with existing managers
- Any assumptions made

This is a narrow-scope task.