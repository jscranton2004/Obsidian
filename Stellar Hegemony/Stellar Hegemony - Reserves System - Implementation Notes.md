# Stellar Hegemony - Reserves System - Implementation Notes

**Status:** Complete (Corrected Model)  
**Date:** 2026-05-29  
**Related Design:** `Stellar Hegemony - Reserves System Design.md` (revised)

## What Was Built

Grok Build delivered the corrected single-pool reserves model.

### Key Changes

**`player_state.gd`** (updated)
- Removed the incorrect separate `reserves` field from the previous attempt.
- `fleets_remaining` (starting at 18) is now the authoritative representation of the player’s total **undeployed** fleets.
- The following methods were repurposed as clean delegates:
  - `get_reserves()` → returns `fleets_remaining`
  - `deploy_from_reserves(amount)` → calls `spend_fleets(amount)`
  - `add_to_reserves(amount)` → calls `add_fleets(amount)`
  - `can_deploy_from_reserves(amount)` → checks against `fleets_remaining`
- `to_dict()` now surfaces `"reserves"` for compatibility.
- Exhaustion logic remains correct (`fleets_remaining <= 0 && !flagship_available`).

**`CardEffectExecutor`** (no changes needed)
- The three relevant cards (`Reinforce`, `Insurrection`, `Emergency Withdrawal`) already worked through the callable context factory.
- They now correctly use the single-pool model with no further changes required.

**Verification**
- `tactic_manager_test.gd` ran cleanly (`exit 0`, zero warnings).
- The model now matches the revised design document exactly.

## How the Model Works

- Players start every game with `reserves = 18`.
- `reserves = fleets_remaining` (the undeployed portion of the fixed 18).
- `deployed = 18 - fleets_remaining` (conceptual; actual on-board count lives in `HybridMap` zones).
- Normal deployment / Reinforce / player side of Insurrection → reduces reserves.
- Emergency Withdrawal / enemy return side of Insurrection → increases reserves.

## Outcome

The Reserves system now correctly follows the single 18-unit pool model. All changes were minimal, preserved existing APIs where possible, and kept the rest of the system (deployment, exhaustion, `TurnManager`, etc.) undisturbed.

---

*Implementation verified against the revised Reserves System Design. Model is now correct.*