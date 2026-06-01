# Stellar Hegemony - Phase 6 Task 12: Deployment Phase End Condition Polish

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-31]]

## Goal
Ensure the Deployment Phase properly ends and transitions in all edge cases, including when the last player exhausts and when there are unusual token or player count scenarios.

## Scope (Narrow)
- Review and strengthen the end condition detection in `DeploymentPhaseManager`.
- Make sure the phase ends cleanly even in low-player or edge token scenarios.
- Ensure the War Phase trigger still fires reliably.
- Do **not** change core logic or add new features — only polish and harden the existing end condition.

## Why This Task
With the full War Phase loop now integrated, it is important to make sure the Deployment Phase end condition is robust before moving on to other areas.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Deployment Phase End Condition Polish (Phase 6 Task 12)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Harden and verify the Deployment Phase end condition so it works reliably in all scenarios.

## Scope (Narrow)
- Review the exhaustion detection and phase end logic in `DeploymentPhaseManager`.
- Ensure the phase ends cleanly and the War Phase trigger fires in edge cases (low player count, unusual token situations, etc.).
- Do **not** change core logic or add new features.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-31]]
- [[Stellar Hegemony - Phase 6 Task 4 - Deployment Phase Structure]]
- [[Stellar Hegemony - Phase 6 Task 11 - War Phase Full Game Loop Integration]]

## Requirements
- End condition must be reliable.
- War Phase trigger must still fire correctly.
- Minimal, well-commented changes.

## Acceptance Criteria
- Deployment Phase ends correctly in all tested scenarios.
- No regression on existing functionality.
- All tests continue to pass cleanly.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*