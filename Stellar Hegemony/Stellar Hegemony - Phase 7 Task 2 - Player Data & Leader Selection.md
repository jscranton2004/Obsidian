# Stellar Hegemony - Phase 7 Task 2: Player Data & Leader Selection

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]], [[Stellar Hegemony - Phase 7 Task 1 - Game Session Manager]]

## Goal
Expand player data handling and add leader selection support inside the game session system so players can choose their leaders during setup.

## Scope (Narrow)
- Enhance `GameSession` (or create supporting structures) to store and manage leader choices per player
- Add methods for setting and validating leader selection
- Support the concept of a leader draft / selection phase
- Keep the system multiplayer-friendly (player IDs, no single-player assumptions)
- No UI yet — pure data and logic layer

## Why This Task
Leader selection is a core part of game setup. Having this working cleanly will make the single-player setup flow (Task 3) much smoother.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Player Data & Leader Selection (Phase 7 Task 2)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Add leader selection support to the game session system.

## Scope (Narrow)
- Store and manage leader choices per player
- Add methods for setting and validating leader selection
- Support the idea of a leader selection/draft phase
- Keep everything multiplayer-friendly (player IDs, no single-player assumptions)
- No UI — data and logic only

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 1 - Game Session Manager]]
- [[Stellar Hegemony - Phase 7 Task 2 - Player Data & Leader Selection]]

## Requirements
- Clean API for assigning and retrieving leaders
- Support for future leader draft flow
- Extensible player data

## Acceptance Criteria
- Players can be assigned leaders
- Leader selection can be validated/restricted if needed
- System remains multiplayer-ready
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 3 once complete.

*Keeping the narrow-scope discipline.*