# Stellar Hegemony - Phase 7 Task 5: Game Loop Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]], [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]], [[Stellar Hegemony - Phase 7 Task 4 - Simple AI Opponent]]

## Goal
Wire the existing systems (`GameSession`, `DeploymentPhaseManager`, `WarPhaseManager`, `SimpleAI`) into a basic playable game loop for single-player.

## Scope (Narrow)
- Create a simple game loop orchestrator that can run a full single-player game
- Handle the flow: Setup → Deployment Phase → War Phase → Repeat
- Integrate the AI opponent so it participates automatically
- Keep it minimal — no UI or scene management yet
- Must remain multiplayer-friendly in design

## Why This Task
With sessions, leader selection, and a basic AI now available, the next step is to connect everything so a full single-player game can actually be played.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Game Loop Integration (Phase 7 Task 5)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Wire the existing systems into a basic playable single-player game loop.

## Scope (Narrow)
- Create a simple game loop that runs Setup → Deployment → War Phase → Repeat
- Integrate the AI opponent so it plays automatically
- Keep it minimal (no UI or scene management)
- Maintain multiplayer-friendly design

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]]
- [[Stellar Hegemony - Phase 7 Task 4 - Simple AI Opponent]]

## Requirements
- A full single-player game can be run from start to finish
- AI participates in deployment automatically
- Clean separation between game loop and individual systems

## Acceptance Criteria
- Can run a complete single-player game loop
- AI makes decisions and plays its turns
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 6 once complete.

*Keeping the narrow-scope discipline.*