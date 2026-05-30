# Stellar Hegemony - Phase 3 Task 3: Zone Ownership Updates After War Phase

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 3 Core Gameplay Plan]]

## Goal
After the War Phase resolution calculates the winner of each zone, update the actual `Zone` nodes so that ownership is correctly assigned.

## Scope (Narrow)
- Connect the results from `WarPhaseManager` to the `Zone` instances
- Call `set_owner_faction()` on each zone with the winning faction
- Handle neutral zones (no one has units)
- Ensure visuals update correctly

## Why This Task
The War Phase manager now determines winners, but the zone ownership state is not yet being updated on the actual `Zone` objects. This task closes that gap.