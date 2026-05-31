# Stellar Hegemony - Phase 6 Task 5: War Phase Trigger

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Implement the automatic War Phase trigger so that when the Deployment Phase ends (all players exhausted), the game cleanly transitions into the War Phase.

## Scope (Narrow)
- Wire `DeploymentPhaseManager` (or `TurnManager`) to detect the end of Deployment and automatically start the War Phase.
- Create the basic War Phase entry point / state.
- Do **not** implement the actual resolution logic (comparing units, applying exhaustion order, ownership changes) yet — only the trigger and phase transition.
- Respect the existing exhaustion system.

## Why This Task
With the Deployment Phase now fully orchestrated, the next natural step is detecting its end and triggering the War Phase so the overall game flow can continue.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: War Phase Trigger (Phase 6 Task 5)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Implement the automatic trigger that ends the Deployment Phase and starts the War Phase.

## Scope (Narrow)
- When `DeploymentPhaseManager` detects that all players have exhausted, automatically transition into War Phase state.
- Create the basic War Phase entry point / manager skeleton.
- Do **not** implement resolution, unit comparison, exhaustion order tiebreakers, or ownership changes yet.
- Keep the transition clean and well-commented.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 4 - Deployment Phase Structure]] (just completed)
- Exhaustion Order Design and Core Mechanics notes

## Requirements
- Automatic detection of Deployment Phase end → War Phase start.
- Clear state management so future War Phase resolution can be added easily.
- No changes to existing Deployment or action logic.

## Acceptance Criteria
- When the last player exhausts, the game automatically enters War Phase.
- Clean separation between Deployment and War phases.
- Well-commented code with explicit Phase 6 Task 5 references.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*