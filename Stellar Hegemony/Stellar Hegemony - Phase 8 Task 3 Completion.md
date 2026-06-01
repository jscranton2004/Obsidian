# Stellar Hegemony - Phase 8 Task 3 Completion

**Status:** Complete  
**Date:** 2026-05-31  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]], [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]], [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]], [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]]

## What Was Delivered

- **New scene:** `scenes/ui/GameSetup.tscn`
  - Minimal, clean UI (VBox + HBoxContainers + Labels + OptionButtons + Buttons)
  - Number of AI Opponents dropdown (1–3)
  - Choose Your Leader dropdown (populated with all 6 canonical leaders using their display_name)
  - Back to Main Menu and Start Game buttons

- **New script:** `scripts/ui/game_setup.gd`
  - Populates the leader dropdown from `LeaderSelection.ALL_LEADERS` on ready
  - On Start Game:
    - Reads selected `num_ai` and leader ID
    - Creates a `GameSession` using the existing Phase 7 helper `create_single_player_session(..., num_ai, ...)`
    - Assigns the chosen leader to the human player via `set_player_leader()`
    - Transitions to `IN_GAME` via `SceneManager`, passing the `GameSession` in transition data
  - On Back: Transitions back to `MAIN_MENU` via `SceneManager`
  - Well-commented and follows the narrow scope exactly

- **Integration:**
  - Updated `scripts/levels/main.gd` to consume a `GameSession` from transition data when arriving from the setup screen.

- **Test:** `scripts/ui/game_setup_test.gd`
  - Lightweight headless verification that the `GameSession` helper supports `num_ai` up to 3 and that all 6 leader IDs are available.

## How to Test

1. Run the project (F5). You should land on the Main Menu.
2. Click Single Player → Game Setup screen should appear.
3. Change the AI count and leader selection.
4. Click Start Game:
   - A `GameSession` is created with the chosen number of AI players.
   - The selected leader is assigned to the human.
   - You should transition into the game (map becomes visible as a placeholder "In Game" state).
5. Click Back to Main Menu from the setup screen — it should return cleanly.

Run the dedicated test:

```
godot --headless --path "C:\Git\stellar-hegemony\game" -s res://scripts/ui/game_setup_test.gd
```

Expected: Clean exit 0 + "TEST COMPLETE".

Also run the full `game_session_test.gd` and `scene_manager_test.gd` for regression.

## Assumptions Made by Grok Build

- "Minimal, clean UI (no heavy styling)" taken literally — plain Godot nodes only.
- The Start Game flow creates the `GameSession` and transitions (full wiring into `DeploymentManager` / `SinglePlayerMatch` etc. left for Task 4).
- Leader selection here is a simple single-choice for the human player.
- The existing `create_single_player_session(num_ai)` helper is the correct integration point.

**Commit:** 052c232

---

**Next step:** Phase 8 Task 4 – In-Game HUD / Flow (connecting the existing game loop to the UI).