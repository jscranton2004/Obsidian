# Stellar Hegemony - Phase 1 Task 3: HybridMap ↔ Zone Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 1 Integration Plan]]

## Goal
Ensure clean, robust communication and data flow between `HybridMap` and the individual `Zone` instances.

## Scope (Narrow)
- Review and improve how `HybridMap` interacts with `Zone` nodes
- Ensure signals, state updates, and data passing are clean and consistent
- Remove any duplication or tight coupling
- Make sure zone highlighting, selection, and updates flow properly through the map

## Why This Task
While deployment and end-of-turn now work, the integration layer between the map controller and individual zones may need refinement for maintainability as more features are added.