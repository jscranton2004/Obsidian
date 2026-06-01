# Stellar Hegemony - Phase 7 Task 1: Game Session Manager (Core)

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]]

## Goal
Create a `GameSession` (or `GameManager`) class that can create and manage game sessions, register players, and handle basic game state in a way that supports both single-player and future multiplayer.

## Scope (Narrow)
- Create a new `GameSession` class
- Ability to create a session and add/remove players
- Store basic player data (ID, name, leader, color/faction)
- Track simple game state (phase, players, etc.)
- Designed from the start with multiplayer in mind (player slots, IDs, no hardcoded local player assumptions)
- No UI, no scene management, no AI yet

## Why This Task
This is the foundation for everything in Phase 7. Without a solid session/player management layer, adding single-player mode or AI becomes messy.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Game Session Manager - Core (Phase 7 Task 1)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create a `GameSession` class that can create and manage game sessions and players.

## Scope (Narrow)
- New `GameSession` class
- Create session + add/remove players
- Store basic player data (player_id, name, leader, faction/color)
- Simple game state tracking
- Must be designed for future multiplayer (player IDs, slots, no single-player assumptions)

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 1 - Game Session Manager]]

## Requirements
- Clean, simple API
- Player data should be extensible
- No UI or game logic yet

## Acceptance Criteria
- Can create a session and add 2–4 players
- Player data is stored correctly
- Designed with multiplayer in mind
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 2 once complete.

*Keeping the narrow-scope discipline.*