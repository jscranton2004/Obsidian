# Stellar Hegemony - Phase 6 Task 11: War Phase Full Game Loop Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-31]]

## Goal
Wire the existing War Phase components into the main game loop so that after the Deployment Phase ends, the War Phase automatically executes (resolve → apply ownership → visual feedback) and the game state is updated.

## Scope (Narrow)
- Add the integration point (likely in `DeploymentPhaseManager` or a top-level `GameManager` / `TurnManager`) that calls the War Phase flow when Deployment ends with `"all_players_exhausted"`.
- Ensure `resolve_war_phase()` → `apply_war_phase_results()` → visual feedback runs automatically.
- Do **not** implement new UI, scoring, or end-of-game logic yet.
- Keep the integration minimal and well-commented.

## Why This Task
The core War Phase pieces (Tasks 5–9) are complete. The next natural narrow step is connecting them to the main game flow so the full Deployment → War Phase cycle becomes playable.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: War Phase Full Game Loop Integration (Phase 6 Task 11)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Wire the existing War Phase components into the main game loop so the War Phase runs automatically after Deployment ends.

## Scope (Narrow)
- Add the integration point that triggers the War Phase when `DeploymentPhaseManager` ends with reason `"all_players_exhausted"`.
- Call the existing flow: `resolve_war_phase()` → `apply_war_phase_results()` → visual feedback.
- Do **not** add new UI, scoring, or end-of-game logic.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-31]]
- [[Stellar Hegemony - Phase 6 Task 5 - War Phase Trigger]]
- [[Stellar Hegemony - Phase 6 Task 8 - War Phase Ownership Application]]
- [[Stellar Hegemony - Phase 6 Task 9 - War Phase Visual Feedback]]

## Requirements
- Clean integration point (likely in DeploymentPhaseManager or TurnManager).
- War Phase runs automatically at the correct moment.
- No changes to the existing War Phase methods themselves.

## Acceptance Criteria
- After Deployment ends, War Phase resolution, ownership application, and visuals all execute automatically.
- Game state is correctly updated.
- All existing tests continue to pass.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*