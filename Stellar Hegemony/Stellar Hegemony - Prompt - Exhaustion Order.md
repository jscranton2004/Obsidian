# Prompt for Grok Build: Exhaustion Order

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Exhaustion Order system that tracks when players run out of units and provides tiebreaker priority based on exhaustion sequence.

## Key Reference Documents
- `Stellar Hegemony - Exhaustion Order Design.md`
- `Stellar Hegemony - Turn Structure Design.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`

## Requirements

### Scope (Narrow)
Focus only on detecting exhaustion and recording order. Do **not** implement War phase, combat, or scoring.

### Core Behavior
- Detect when a player’s token pool reaches zero units.
- Record the exact moment (global turn count or timestamp) a player exhausts.
- Maintain a ranked list of exhaustion order (1st exhausted = highest priority).
- Provide a method to compare two players for tiebreaker purposes.

### Tracking
- Store exhaustion data per player (turn number exhausted + rank).
- Once exhausted, the rank is permanent.
- Players who never exhaust during the game have the lowest priority.

### Integration
- Listen to `PlayerState` pool changes (or be notified when pool reaches zero).
- Work alongside the existing `TurnManager` (which already calls `lock_pool_for_exhaustion()`).
- Store data in or alongside `PlayerState`.

### Query API (minimum)
- `is_player_exhausted(player_id)`
- `get_exhaustion_rank(player_id)` — lower number = exhausted earlier = better tiebreaker
- `compare_exhaustion_priority(player_a, player_b)` — returns which player wins a tie

## Acceptance Criteria
- Players who exhaust earlier receive higher tiebreaker priority.
- Exhaustion is detected automatically when a player’s pool hits zero.
- The system provides reliable comparison for future War phase use.
- No War or combat logic is implemented.

## Files You Will Likely Touch
- `game/scripts/systems/` (new `exhaustion_manager.gd` or extend `PlayerState`)

## Important Notes
- Keep the implementation focused and minimal.
- Build on top of the existing `PlayerState` and `TurnManager`.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How exhaustion order is tracked and compared
- Any assumptions made

This is a narrow-scope task.