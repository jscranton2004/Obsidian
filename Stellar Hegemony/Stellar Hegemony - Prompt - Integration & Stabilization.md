# Prompt for Grok Build: Integration & Stabilization

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Wire the existing managers together so they work as a cohesive system, with `PlayerState` as the central source of truth.

## Key Reference Documents
- `Stellar Hegemony - Integration & Stabilization Design.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`
- `Stellar Hegemony - Card Effect Executor - Implementation Notes.md`

## Requirements

### Scope (Narrow)
Focus on integration and data consistency. Do not implement full turn structure or War phase.

### Primary Tasks

1. **Automatic Effect Execution**
   - Modify `TacticManager.player_use_card()` so that when a `CardEffectExecutor` is attached, it automatically executes the card effect instead of requiring manual `_and_execute` calls.

2. **PlayerState as Source of Truth**
   - Update `CardEffectExecutor` and `CardExecutionContext` to consistently read from and write to `PlayerState` objects.
   - Reduce reliance on raw dictionaries for player data.

3. **Improved Context Creation**
   - Create a clean factory/helper method to build a `CardExecutionContext` from the current game state (`DeploymentManager`, `HybridMap`, etc.).

### Acceptance Criteria

- Calling `TacticManager.player_use_card()` automatically executes the card effect when an executor is available.
- `PlayerState` is used consistently across `DeploymentManager`, `TacticManager`, and `CardEffectExecutor`.
- `CardExecutionContext` can be created cleanly from the managers.

## Files You Will Likely Touch
- `game/scripts/systems/tactic_manager.gd`
- `game/scripts/systems/card_effect_executor.gd`
- `game/scripts/systems/deployment_manager.gd`
- Possibly `game/scripts/systems/player_state.gd`

## Important Notes
- Keep changes minimal and safe.
- Preserve backward compatibility where reasonable (e.g., `get_player_pool()`).

Please implement this cleanly with good comments. After completion, briefly describe:
- What was changed
- How the managers now communicate
- Any assumptions made

This is a narrow-scope integration task.