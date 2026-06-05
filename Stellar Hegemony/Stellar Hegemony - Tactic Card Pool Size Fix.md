# Stellar Hegemony - Tactic Card Pool Size Fix

**Date:** 2026-06-05  
**Status:** Complete

## Defect
`TacticManager.create_shared_pool()` hardcoded **4** cards regardless of player count. Planning ([[Stellar Hegemony - Tactic Card System Planning]]) requires **players + 1**.

## Correct Rule (per Rumble Nation / planning)
| Players | Tactic cards in shared pool |
|---------|----------------------------|
| 2 | 3 |
| 3 | 4 |
| 4 | 5 |

**Note:** Leader draft uses the same **players + 1** formula but is a **separate** system (`LeaderSelection`). The Deployment UI shows tactic pool cards in the tactic list and the player's leader ability on its own button — not mixed into the tactic pool.

## Fix
- `game/scripts/systems/tactic_manager.gd` — `desired_count := num_players + 1`
- `game/scripts/systems/tactic_manager_test.gd` — updated size assertions

*See also: [[Stellar Hegemony - Tactic Card System - Implementation Notes]]*