# Stellar Hegemony - Phase 8 Task 4: In-Game HUD / Flow

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]], [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]], [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]], [[Stellar Hegemony - Phase 7 Task 1 Completion]]

## Goal
Connect the existing game loop (DeploymentPhaseManager, WarPhaseManager, SinglePlayerMatch, etc.) to the new SceneManager flow so that when a GameSession is passed into the IN_GAME state, the game actually becomes playable with basic UI feedback.

## Scope (Narrow)
- Create a lightweight InGame scene / HUD
- On entering IN_GAME state with a GameSession in transition data:
  - Instantiate or reference the existing game systems (SinglePlayerMatch or equivalent)
  - Display basic player info (current leader, phase, turn number)
  - Show a simple "End Turn" button that respects the one-action-per-turn rule
- Use SceneManager for any transitions (e.g. back to setup or main menu if needed)
- Keep UI minimal and clean
- Do **not** implement full deployment UI, war phase visuals, or new mechanics — just wire the existing systems so the game loop is reachable from the menu

## Why This Task
Tasks 1–3 gave us menus and session creation. Task 4 is the critical bridge that makes the Phase 7 game systems actually reachable and controllable from the new UI flow. This is the point where the game becomes "playable end-to-end" from the main menu.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: In-Game HUD / Flow (Phase 8 Task 4)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Wire the existing game systems into the SceneManager IN_GAME state so a GameSession created from the setup screen actually runs.

## Scope (Narrow)
- Create a lightweight InGame scene / HUD
- On entering IN_GAME with a GameSession in transition data:
  - Start the game loop using existing systems (SinglePlayerMatch / DeploymentPhaseManager / WarPhaseManager)
  - Display basic HUD info: current player leader, current phase, turn number
  - Add a simple "End Turn" button that calls the appropriate method on the active phase manager
- Use SceneManager for transitions
- Keep UI minimal and clean (plain Godot nodes)
- Do not implement new mechanics, full deployment UI, or war visuals

## Key References
- [[Stellar Hegemony - Phase 8 - Overview]]
- [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]]
- [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]]
- [[Stellar Hegemony - Phase 7 Task 1 Completion]] (GameSession + SinglePlayerMatch)
- Phase 6 War Phase and Deployment systems

## Requirements
- GameSession passed from setup must be consumed and the game loop started
- Basic HUD visible and functional
- End Turn button works and respects exhaustion rules
- Clean transitions via SceneManager

## Acceptance Criteria
- Starting a game from the setup screen lands in a playable IN_GAME state
- HUD shows correct player/phase/turn info
- End Turn button advances the turn
- All existing tests (game_session, scene_manager, game_setup) still pass
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 5 (Settings Menu) once complete.

*Keeping the narrow-scope discipline.*