# Stellar Hegemony - Phase 6 Task 9: War Phase Visual Feedback

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Add basic visual feedback when War Phase resolution and ownership application occur, so players can see the results of the War Phase.

## Scope (Narrow)
- Wire simple signals or calls from `WarPhaseManager` after `apply_war_phase_results()`.
- Trigger basic ownership change visuals on zones (e.g., material/color update or simple highlight).
- Do **not** implement full animations, particle effects, or detailed combat visuals yet.
- Keep the implementation minimal and focused on making the ownership change visible.

## Why This Task
With resolution and ownership application now working, the next natural narrow step is giving the player some visual indication that the War Phase has had an effect.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: War Phase Visual Feedback (Phase 6 Task 9)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Add basic visual feedback after War Phase ownership changes so players can see the results.

## Scope (Narrow)
- After `apply_war_phase_results()`, trigger basic visual updates on affected zones.
- Use existing zone material or simple color changes to reflect new ownership.
- Do **not** implement complex animations, particles, or combat visuals.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 8 - War Phase Ownership Application]]
- Zone and HybridMap notes

## Requirements
- Visual feedback should be triggered automatically after ownership application.
- Keep it simple and performant.
- Well-commented code.

## Acceptance Criteria
- Zones visually update to reflect new ownership after War Phase.
- No performance issues on modest hardware.
- Clean integration with existing zone rendering.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*