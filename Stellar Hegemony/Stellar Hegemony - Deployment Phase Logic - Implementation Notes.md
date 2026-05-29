# Stellar Hegemony - Deployment Phase Logic - Implementation Notes

**Implemented:** 2026-05-29 by Grok Build  
**Status:** Complete (narrow scope)

## What Was Delivered

### Primary Deliverable
- `game/scripts/systems/deployment_manager.gd`
  - New `DeploymentManager` class (extends `RefCounted`)
  - Handles a **single deployment action** from the dice signal

### Key Features Implemented
- Correct mapping of `unit_value` (1–6) → 1 / 2 / 3 units
- Target zone resolution using the existing `HybridMap.get_zone_by_value()`
- Per-player token pools (18 Fleets + 1 Flag Ship)
- Full support for the two special low-token edge cases from the planning document:
  - 1 token left + die wants 3 → place 1
  - 1 Fleet + 1 Leader left + die wants 3 → place both
- Optional `include_flagship: bool` parameter when calling `perform_deployment()`
- Automatic update of the target `Zone` (using the existing `fleet_count` / `has_flagship` system)
- Rich result dictionary + debug output for every action
- Optional one-line wiring to the existing `DeploymentDiceUI` signal

### Supporting File
- `game/scripts/systems/deployment_manager_test.gd` — Headless + in-editor runnable test covering normal placements, both special cases, Flag Ship choice, and zero-token handling.

### Scope Discipline
- No other files were modified.
- No full multi-player deployment round.
- No War phase or combat.
- No UI for choosing whether to place the Flag Ship.
- No exhaustion order tracking.

## How to Test

**Recommended (headless verification):**
```bash
godot --headless --path "C:\Git\stellar-hegemony\game" -s "res://scripts/systems/deployment_manager_test.gd"
```

**Live visual test (with existing dice UI + unit visuals):**
Temporarily add the manager to `Main.tscn` and connect it to `DeploymentDiceUI`. Roll dice, choose your split, hit Confirm, and watch the zone icons update live (fleets + optional Flag Ship with correct tint and distinction).

## Assumptions Made
- Player identity is a simple string key for now.
- Each player is associated with one faction at initialization.
- The `include_flagship` decision is supplied by the caller (no UI/AI logic yet).
- The manager is instantiated on demand (can later live inside a `GameManager`).
- Exhaustion order and ability lockout are explicitly out of scope for this slice.

---

*Clean, focused implementation that directly satisfies the narrow-scope requirements.*