# Stellar Hegemony - Leader Selection System - Implementation Notes

**Implemented:** 2026-05-29 by Grok Build  
**Status:** Complete (narrow scope)

## What Was Delivered

### Primary File
- `game/scripts/systems/leader_selection.gd`
  - New `systems/` folder created
  - `LeaderSelection` class (extends `RefCounted`)
  - Full implementation of the requested logic

### Key Features Implemented
- Exact 6 leaders with full names + titles (from Adapted Flag Ship Cards)
- `start_new_game(players: int)` — main entry point
- Randomly offers exactly `(players + 1)` leaders (always excludes 1 when 4 players)
- Generates random turn order
- Computes **reverse picking order** so the last player picks first
- `pick_leader(player_index, leader_id)` enforces correct picking sequence
- Rich getter API:
  - `get_offered_leaders()`
  - `get_turn_order()`
  - `get_picking_order()`
  - `get_available_leaders()`
  - `get_next_player_to_pick()`
  - `is_selection_complete()`
  - `get_leader_for_player()`
- `auto_assign_for_testing()` helper
- Extensive comments referencing Core Mechanics

### Supporting File
- `game/scripts/systems/leader_selection_test.gd` — headless test runner (can be kept or deleted)

### What Was Not Touched (per instructions)
- No changes to `hybrid_map.gd`
- No UI
- No Player/Faction data model
- No leader card effects

## How to Test

**Recommended (headless verification):**
```bash
godot --headless --path "C:\Git\stellar-hegemony\game" -s "res://scripts/systems/leader_selection_test.gd"
```

This runs multiple simulations for 2/3/4 players and verifies all acceptance criteria.

**Manual usage example:**
```gdscript
var draft := preload("res://scripts/systems/leader_selection.gd").new()
draft.start_new_game(3)

print(draft.get_offered_leaders())      # 4 leaders
print(draft.get_picking_order())        # e.g. [2, 0, 1] — player 2 picks first
```

## Assumptions Made (kept narrow)
- Players represented as simple integers (0..n-1)
- Turn order is always freshly randomised
- Class is instantiated on demand (`new()`) rather than as an autoload
- No persistence or asset wiring

## Next Natural Steps (not yet implemented)
- Leader selection UI (draft screen)
- Lightweight `GameManager` autoload that owns this + the zone value system
- Wiring chosen leaders to actual player/faction instances
- Tactic cards

---

*Documented for team reference and future integration work.*