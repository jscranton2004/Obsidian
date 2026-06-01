# Stellar Hegemony - Phase 8 Task 1: Scene Manager / Game State Machine

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]]

## Goal
Create a central `SceneManager` (or `GameStateMachine`) that handles scene transitions and tracks the overall game state in a clean, maintainable way.

## Scope (Narrow)
- Create a `SceneManager` singleton or autoload
- Define core game states (MainMenu, GameSetup, InGame, WarPhase, GameOver, etc.)
- Provide simple methods for changing scenes (`change_scene()`, `reload_current()`, etc.)
- Support passing data between scenes when needed
- Keep it lightweight and focused on scene flow (no game logic)

## Why This Task
A solid scene manager is the foundation for all UI and flow work in Phase 8. Doing this first ensures the rest of the menus and game flow have a consistent way to transition.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Scene Manager (Phase 8 Task 1)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create a central SceneManager for handling scene transitions and game state.

## Scope (Narrow)
- New SceneManager (autoload or singleton)
- Core game states (MainMenu, GameSetup, InGame, etc.)
- Simple scene changing API
- Support for passing data between scenes
- Lightweight — no game logic

## Key References
- [[Stellar Hegemony - Phase 8 - Overview]]
- [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]]

## Requirements
- Clean, reusable scene transition system
- Easy to extend with new states
- Well-documented

## Acceptance Criteria
- Can change between defined scenes
- Game state is tracked centrally
- Works with both single-player and future multiplayer flows
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 2 (Main Menu) once complete.

*Keeping the narrow-scope discipline.*