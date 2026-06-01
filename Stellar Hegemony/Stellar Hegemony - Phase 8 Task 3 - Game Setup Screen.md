# Stellar Hegemony - Phase 8 Task 3: Game Setup Screen

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]], [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]], [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]], [[Stellar Hegemony - Phase 7 Task 1 Completion]]

## Goal
Create a basic Game Setup screen that allows the player to configure a single-player match (leader selection + number of AI opponents) before starting the game.

## Scope (Narrow)
- Create a simple `GameSetup` scene (using Godot's UI system)
- UI elements for:
  - Number of AI opponents (1–3, respecting the 4-player max)
  - Leader selection (for the human player)
  - Start Game button
- Use `SceneManager` for all transitions (back to Main Menu, forward into the game)
- Keep the UI minimal and clean (no complex styling yet)
- Integrate with the existing `GameSession.create_single_player_session()` method from Phase 7

## Why This Task
With the Main Menu and SceneManager in place, the next logical step is to give the player a proper way to set up a game before entering the actual gameplay loop. This bridges the menu system with the core game systems.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Game Setup Screen (Phase 8 Task 3)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create a basic Game Setup screen.

## Scope (Narrow)
- Simple GameSetup scene with UI elements
- Options for:
  - Number of AI opponents (1–3, since max 4 players total)
  - Leader selection (dropdown or buttons for the 6 available leaders)
  - Start Game button
- Use SceneManager for transitions (back to Main Menu, forward to game)
- Minimal, clean UI (no heavy styling)
- Support the existing GameSession.create_single_player_session() method

## Key References
- [[Stellar Hegemony - Phase 8 - Overview]]
- [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]]
- [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]]
- [[Stellar Hegemony - Phase 7 Task 1 Completion]] (GameSession single-player support)

## Requirements
- Functional setup screen that collects player count and leader choice
- Proper transitions via SceneManager
- Easy to extend later (multiplayer setup will build on this)

## Acceptance Criteria
- Game Setup scene loads correctly from Main Menu
- Can select number of AI players and a leader
- Start Game button successfully creates a GameSession and transitions into the game
- Well-commented code and scene

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 4 (In-Game HUD / Flow) once complete.

*Keeping the narrow-scope discipline.*