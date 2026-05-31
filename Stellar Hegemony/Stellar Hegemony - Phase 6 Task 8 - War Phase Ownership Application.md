# Stellar Hegemony - Phase 6 Task 8: War Phase Ownership Application

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Implement the application of War Phase resolution results so that zone ownership is correctly updated based on the winners determined during resolution.

## Scope (Narrow)
- Add `apply_war_phase_results()` (or similar) in `WarPhaseManager`.
- Take the resolution records from `resolve_war_phase()` and update zone ownership accordingly.
- Handle the case where a zone changes hands.
- Do **not** implement visual feedback or scoring yet — only the ownership state change.
- Keep changes minimal and well-commented.

## Why This Task
With pure resolution now working, the next natural narrow step is applying those results to actually change zone ownership.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: War Phase Ownership Application (Phase 6 Task 8)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Implement the application of War Phase resolution results to update zone ownership.

## Scope (Narrow)
- Add `apply_war_phase_results(resolution_results)` in `WarPhaseManager`.
- For each resolution record, update the owning player on the corresponding zone.
- Handle ownership changes cleanly.
- Do **not** trigger any visuals, scoring, or UI yet.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 7 - War Phase Resolution]]
- Core Mechanics and Zone Ownership notes

## Requirements
- Ownership updates must be based strictly on the resolution records.
- Clean separation between resolution and application.
- Well-commented code.

## Acceptance Criteria
- `apply_war_phase_results()` correctly updates zone ownership based on resolution winners.
- No side effects outside of ownership state.
- All existing tests continue to pass.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*