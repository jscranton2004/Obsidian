# Stellar Hegemony - Phase 7 Task 3: Single Player Setup

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]], [[Stellar Hegemony - Phase 7 Task 1 - Game Session Manager]], [[Stellar Hegemony - Phase 7 Task 2 - Player Data & Leader Selection]]

## Goal
Enable the creation of a single-player game session, including the ability to add an AI opponent slot alongside the human player.

## Scope (Narrow)
- Add support in `GameSession` (or a helper) for marking players as AI-controlled
- Provide a simple way to create a single-player game (1 human + 1 AI)
- Keep the system multiplayer-friendly (AI players are just another player type)
- No actual AI behavior yet (that comes in Task 4)
- No UI — data and logic only

## Why This Task
Having a clean way to set up single-player games will make it much easier to test the full game loop and will be the foundation for adding AI behavior in the next task.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Single Player Setup (Phase 7 Task 3)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Add support for creating single-player game sessions (human + AI opponent).

## Scope (Narrow)
- Add the concept of AI-controlled players in GameSession
- Provide a clean way to create a single-player game (1 human + 1 AI)
- Keep the system multiplayer-friendly (AI is just another player type)
- No actual AI behavior or decision-making yet
- No UI — data and logic only

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 1 - Game Session Manager]]
- [[Stellar Hegemony - Phase 7 Task 2 - Player Data & Leader Selection]]

## Requirements
- Clean way to mark a player as AI-controlled
- Easy single-player session creation helper (optional but recommended)
- Maintains multiplayer compatibility

## Acceptance Criteria
- Can create a session with 1 human + 1 AI player
- AI players are clearly distinguishable from human players
- System remains extensible for future multiplayer
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 4 (AI Opponent) once complete.

*Keeping the narrow-scope discipline.*