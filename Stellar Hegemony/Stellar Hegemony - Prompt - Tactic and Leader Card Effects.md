# Prompt for Grok Build: Tactic and Leader Card Effects

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the actual effects for Tactic Cards and Leader (Flag Ship) Cards.

## Key Reference Documents
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md` (primary reference)
- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - Adapted Flag Ship Cards.md`
- `Stellar Hegemony - Zone Connectivity System Design.md`

## Requirements

### Scope (Narrow)
Focus on building the **effect execution logic** only. Do not implement UI, card selection screens, or full game flow.

### Core Architecture
Create a `CardEffectExecutor` (or `EffectSystem`) that can execute effects when given:
- Card/Leader ID
- Player performing the action
- A `CardExecutionContext` containing access to `HybridMap`, unit data, reserves, and connectivity queries

### Key Behaviors
- Effects must correctly use the **Zone Connectivity System**:
  - `get_adjacent_zones()` for standard movement
  - `get_hyperspace_connected_zones()` for hyperspace-only effects
  - `get_wormhole_connected_zones()` for wormhole-only effects
- Effects must respect the current **Unit Representation** system (Fleets + Flag Ships as units)
- Partial execution is allowed when a player has fewer units than the card requires
- "Can perform the action" eligibility checks should be supported via helper methods

### Cards to Implement
All 12 Tactic Cards and 6 Leader Cards as listed in the design document.

## Acceptance Criteria

- Effects correctly distinguish between standard adjacency and route-specific movement
- Movement, replacement, and reserve interactions work as described in the card text
- The executor can be called from `TacticManager.player_use_card()` and a future leader usage method
- Effects integrate cleanly with the existing `Zone` and `HybridMap` systems

## Files You Will Likely Touch
- `game/scripts/systems/` (new `card_effect_executor.gd` recommended)
- Possibly minor updates to `hybrid_map.gd` or `zone.gd` for helper methods

## Important Notes
- Each card can only be used once per game (already enforced by the managers)
- The "must be able to perform the action" check is the caller's responsibility but should be supported by the executor
- Keep this implementation focused on effect logic only

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How to test individual card effects
- Any assumptions made

This is a narrow-scope task.