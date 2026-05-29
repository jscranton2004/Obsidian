# Prompt for Grok Build: Zone Value Assignment System

**Project:** Stellar Hegemony  
**Repo location (on your machine):** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault at `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

**Goal:** Implement the missing "11 zones with unique random 2–12 values at game start" feature.

This is the exact mechanic described in the Core Mechanics documentation but never implemented in code.

## Key Documentation Reference
Read this file first for the rule:
`C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\Stellar Hegemony - Core Mechanics.md`

Relevant excerpt:
> "At the start of every game, each of the 11 sectors is randomly assigned a **unique** point value between **2 and 12** (each value is used exactly once). These values are **not** fixed to any specific sector — they are reassigned every game."

These values are used for both:
- Dice targeting during deployment
- End-of-game victory points

## Current Code State (what already exists in the repo)

**Files:**
- `game/scripts/map/zone.gd` — contains `@export var zone_value: int`
- `game/scripts/map/hybrid_map.gd` — contains:
  - `get_zone_by_value(value)` method (already used by the dice system)
  - `M1_ZONE_DATA` constant with only 7 hardcoded zones (this is placeholder)
- `game/scenes/Map/HybridMap.tscn` — currently has static zone children

The dice deployment system (`DeploymentDiceUI`) already calls `get_zone_by_value()` successfully.

## What Needs to Be Built (narrow scope only)

Create a **Zone Value Assignment System** with this exact behaviour:

1. At the start of a new game, ensure there are exactly **11 zones**.
2. Randomly assign each zone a **unique** value from the set `{2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}` (every number used exactly once per game).
3. Store the assigned value in each zone’s `zone_value` property.
4. These values must persist for the entire game and be re-randomized on the next new game.

## Strict Requirements

- Follow the existing code style and naming conventions already used in `hybrid_map.gd` and `zone.gd`.
- Replace the hardcoded 7-zone `M1_ZONE_DATA` approach with proper dynamic 11-zone creation + random unique assignment.
- The assignment must happen once at game start (via `new_game()`, `_ready()`, or a dedicated `setup_zones()` method).
- Keep `get_zone_by_value(value)` working so the existing dice deployment system continues to function.
- Do **not** implement scoring, victory conditions, zone visuals, or spawning logic — only the value assignment system.

## Acceptance Criteria (must pass these)

- A new game always creates exactly 11 zones.
- The 11 zones receive unique values 2 through 12 (no duplicates, no missing numbers).
- `get_zone_by_value(7)` returns the zone that was randomly given the value 7 this game.
- Running the game multiple times produces different random assignments.
- The dice deployment system continues to work without modification.
- The assigned values are stable for the duration of one game.

## Files You Are Expected to Modify
- `game/scripts/map/hybrid_map.gd` (main logic)
- `game/scripts/map/zone.gd` (minor updates if needed)
- Possibly `game/scenes/Map/HybridMap.tscn` (if dynamic instantiation is required)

Please implement this cleanly, add clear comments explaining the random assignment logic, and verify that the dice deployment system still works after your changes.

After implementation, briefly describe:
- What files were changed
- How to test the new behaviour
- Any assumptions you made

This is a narrow-scope task. Stay focused on the random unique value assignment only.