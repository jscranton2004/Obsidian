# Stellar Hegemony - Phase 6 Task 6: Global Ability Lockout

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Fully enforce the global ability lockout so that once any player exhausts, **all** players immediately lose access to both Tactic cards and Leader abilities for the remainder of the Deployment Phase.

## Scope (Narrow)
- Ensure the global lockout (already partially implemented via `TacticManager`) is correctly respected by the new `DeploymentPhaseManager` and `WarPhaseManager`.
- Block Tactic and Leader usage globally the moment the first player exhausts.
- Make sure the lockout is properly lifted only at the start of the next Deployment Phase.
- Do not change the core exhaustion tracking logic.

## Why This Task
The global lockout rule is a core part of the original Rumble Nation design. With the phase managers now in place, we need to make sure the lockout is reliably enforced across the entire system.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Global Ability Lockout (Phase 6 Task 6)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Make the global ability lockout fully reliable across DeploymentPhaseManager and WarPhaseManager.

## Scope (Narrow)
- Ensure that when the first player exhausts, both Tactic and Leader abilities are immediately blocked for **all** players.
- Verify the lockout is respected by `get_available_actions()` and `perform_action()`.
- Ensure the lockout is correctly cleared at the start of a new Deployment Phase.
- Do not modify the underlying exhaustion or `TacticManager.lock_pool_for_exhaustion()` logic.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 5 - War Phase Trigger]]
- [[Stellar Hegemony - Phase 6 Task 4 - Deployment Phase Structure]]
- TacticManager and Exhaustion Order Design notes

## Requirements
- Global lockout must affect both Tactic and Leader abilities.
- Lockout must be enforced at the `DeploymentPhaseManager` level.
- Clean, minimal changes with good comments.

## Acceptance Criteria
- Once any player exhausts, no player can use Tactic or Leader abilities until the next Deployment Phase.
- `get_available_actions()` correctly reflects the global lockout.
- All existing tests continue to pass.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*