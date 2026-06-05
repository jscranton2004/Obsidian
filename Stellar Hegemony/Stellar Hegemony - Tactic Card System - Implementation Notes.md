# Stellar Hegemony - Tactic Card System - Implementation Notes

**Implemented:** 2026-05-29 by Grok Build  
**Status:** Complete (narrow scope)

## What Was Delivered

### Primary Deliverable
- `game/scripts/systems/tactic_manager.gd`
  - New `TacticManager` class (consistent with `LeaderSelection` and `DeploymentManager`)

### Key Features Implemented
- `create_shared_pool(num_players)` — randomly selects exactly **(num_players + 1)** cards from the 12 into a shared pool (2→3, 3→4, 4→5)
- `get_available_cards()` / `get_pool_ids()` — returns current shared pool
- `can_player_select_card(player_id, card_id, is_eligible)` — enforces:
  - Pool membership
  - Per-player limit (only 1 tactic ever)
  - Global lockout
  - "Can perform the action" requirement (via `is_eligible` boolean passed by caller)
- `player_use_card(...)` — removes the card from the shared pool permanently and marks the player as having used their one card
- `lock_pool_for_exhaustion()` + `is_pool_locked()` — implements the global lockout rule
- Full 12-card definitions (id + name + description) in `TacticManager.ALL_TACTIC_CARDS` — see **Card Rules** below
- `get_card_definition(card_id)` (Phase 10 Task 11) — pool-independent lookup for UI popup text
- Excellent comments referencing the planning docs

### Supporting File
- `game/scripts/systems/tactic_manager_test.gd` — self-contained test script that verifies every acceptance criterion (pool sizes for 2/3/4 players, 1-per-player limit, removal from shared pool, eligibility gating, and global lockout)

No other files were modified.

## Card Rules (Canonical)

**Source of truth in code:** `game/scripts/systems/tactic_manager.gd` → `ALL_TACTIC_CARDS`  
**Design reference:** [[Stellar Hegemony - Adapted Tactic Cards]]  
**UI lookup (popup descriptions):** `TacticManager.get_card_definition(card_id)` — always reads from `ALL_TACTIC_CARDS`, not the runtime pool.

**Important rule (adjacency):**
- “Adjacent” = hyperspace lanes **or** wormholes
- Cards specifying “via hyperspace lanes” or “via wormhole” are restricted to that route only

### Movement Cards

| ID | Name | Rules Text |
|----|------|------------|
| `scout` | Scout | Move 1 of your FLEETS to an adjacent system. |
| `hyperspace_invasion` | Hyperspace Invasion | Move 2 of your FLEETS from 1 system to an adjacent system via hyperspace lanes. |
| `wormhole_invasion` | Wormhole Invasion | Move 2 of your FLEETS from 1 system to an adjacent system via wormhole. |
| `sub_light_squadron` | Sub-Light Squadron | Move ½ of your FLEETS (rounded down) from 1 system to an adjacent system. |
| `shadow_fleet` | Shadow Fleet | Move 1 of your FLEETS to any system where you already have FLEETS. |
| `converge_on_the_core` | Converge on the Core | Move any number of your FLEETS to the Core System from systems adjacent to it. |

### Support & Disruption Cards

| ID | Name | Rules Text |
|----|------|------------|
| `reinforce` | Reinforce | Deploy 1 FLEET from your reserves into any system where you already have FLEETS. |
| `insurrection` | Insurrection | Return 1 enemy FLEET to its reserves and replace it with a FLEET from your reserves. |
| `expel` | Expel | Move 1 enemy FLEET from a system where you have FLEETS to an adjacent system. |
| `seize` | Seize | Move 1 enemy FLEET from any system to an adjacent system where you have FLEETS. |
| `false_flag` | False Flag | Move 1 of your FLEETS along with 2 enemy FLEETS to an adjacent system. |
| `emergency_withdrawal` | Emergency Withdrawal | Return 2 of your FLEETS from any system(s) to your reserves. |

## How to Test

**Easiest (recommended):**
1. In the Godot editor, create a temporary scene or add a `Node` to `Main.tscn`.
2. Attach `res://scripts/systems/tactic_manager_test.gd` to it.
3. Press Play. It prints detailed pass/fail results to the Output panel and quits.

**Manual / live testing in editor or console:**
```gdscript
var tm := TacticManager.new()
tm.create_shared_pool(3)          # 4 cards in pool (3 players + 1)
print(tm.get_pool_ids())          # should have (players + 1) random ids

# p1 uses one (eligible)
tm.player_use_card("p1", tm.get_pool_ids()[0], true)

# p1 cannot use another
assert(not tm.can_player_select_card("p1", "...", true))

# Global lockout (simulating a player running out of units)
tm.lock_pool_for_exhaustion()
assert(not tm.can_player_select_card("p2", "...", true))
```

## Integration Notes (from Grok)
- When any player exhausts their last unit (via `DeploymentManager`), call `tactic_manager.lock_pool_for_exhaustion()`.
- The caller is responsible for computing the `is_eligible` boolean for each card based on current board state.

## Assumptions Made
- "Can perform the action" eligibility is supplied by the caller (`is_eligible: bool`).
- Player identity uses simple string IDs (consistent with other managers).
- The 12 cards are defined with stable ids + descriptions.
- Global lockout is a simple boolean flag + public method.
- No UI, no turn system, no actual card effects, and no Leader card logic (all explicitly out of scope).

---

*Focused, well-commented implementation that satisfies every acceptance criterion while staying strictly within the narrow scope.*