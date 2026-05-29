# Prompt for Grok Build: Zone Value Assignment System

**Goal:** Implement the missing "11 zones with unique random 2–12 values at game start" feature.

This is the exact feature described in the Core Mechanics and referenced in the comments of the existing code, but never implemented.

## Current State (what already exists)
- `scripts/map/zone.gd` has `@export var zone_value: int` with the correct comment.
- `scripts/map/hybrid_map.gd` has:
  - `get_zone_by_value(value)` method (used by the dice deployment system)
  - `M1_ZONE_DATA` constant with only 7 hardcoded zones
- Zones currently exist as static child nodes in `scenes/Map/HybridMap.tscn`
- Dice deployment UI already calls `get_zone_by_value()` successfully

## What Needs to Be Built (narrow scope)

Create a proper **Zone Value Assignment System** that runs at game start with the following behaviour:

1. When a new game begins, create (or reset) exactly **11 zones**.
2. Randomly shuffle and assign each zone a **unique** value from the set `{2,3,4,5,6,7,8,9,10,11,12}` (each number used exactly once).
3. Store the assigned `zone_value` on each zone so it can be used for:
   - Dice targeting during deployment (already works via `get_zone_by_value`)
   - End-of-game scoring / victory points

## Requirements & Constraints

- Follow the existing code style and naming in `hybrid_map.gd` and `zone.gd`.
- Do **not** hardcode the 7-zone `M1_ZONE_DATA` for the final version — replace it with dynamic 11-zone creation + random assignment.
- The assignment must happen once at the start of a game (or on a `new_game()` / `setup()` call).
- The values must remain stable for the rest of that game (no re-rolling mid-game).
- Keep the `get_zone_by_value(value)` method working (or update it if needed).
- Do **not** implement scoring UI, victory conditions, or zone spawning visuals yet — just the data assignment system.

## Acceptance Criteria

- At game start, exactly 11 zones exist with unique values 2–12.
- `get_zone_by_value(7)` returns the correct zone that was randomly assigned 7 this game.
- Running the game multiple times produces different assignments.
- The dice deployment system continues to work without changes.
- No duplicate values are ever assigned in a single game.

## Files You Will Likely Touch
- `scripts/map/hybrid_map.gd`
- `scripts/map/zone.gd` (if minor updates needed)
- Possibly `scenes/Map/HybridMap.tscn` (to support dynamic zone creation)

Please implement this cleanly and comment the new code so the intent is obvious for future team members. After you're done, briefly describe what changed and how to test it.