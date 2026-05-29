# Prompt for Grok Build: Reserves System

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Reserves system so that players have a secondary pool of units that can be moved to and from the board via Tactic Cards.

## Key Reference Documents
- `Stellar Hegemony - Reserves System Design.md`
- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`

## Requirements

### Scope (Narrow)
Add reserves tracking and support the three cards that directly reference reserves. Do **not** implement full card UI or War phase.

### Core Behavior
- Every player has a `reserves` count (separate from their main fleet pool).
- Provide methods to:
  - Add units to reserves (from the board)
  - Deploy units from reserves (to the board)
- Reserves do **not** affect exhaustion state.

### Card Support
Support the following effects (via `CardEffectExecutor` or direct methods):
- **Reinforce**: Move 1 unit from reserves → board (into a system the player already occupies)
- **Insurrection**: Move 1 enemy fleet to its reserves, then move 1 of your units from reserves to that system
- **Emergency Withdrawal**: Move up to 2 of your fleets from the board back to reserves

### Integration
- Store `reserves` in `PlayerState`
- Update `CardEffectExecutor` to handle reserves-related effects
- Ensure `PlayerState` methods are used so the data stays consistent

### Query / Mutation API (minimum)
- `add_to_reserves(player_id, amount)`
- `deploy_from_reserves(player_id, amount)`
- `get_reserves(player_id)`
- `can_deploy_from_reserves(player_id, amount)`

## Acceptance Criteria
- Players can move units to and from reserves.
- The three relevant tactic effects are supported.
- Reserves are tracked separately from the main token pool (and do not affect exhaustion).
- The system is ready for future card execution wiring.

## Files You Will Likely Touch
- `game/scripts/systems/player_state.gd`
- `game/scripts/systems/card_effect_executor.gd`
- Possibly a small `reserves_manager.gd` if it keeps things cleaner

## Important Notes
- Keep the implementation focused and minimal.
- Build on top of the existing `PlayerState` and `CardEffectExecutor`.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How reserves are tracked and used by cards
- Any assumptions made

This is a narrow-scope task.