# Stellar Hegemony - Phase 6 Task 3: Leader Ability Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Integrate Leader (Flag Ship) abilities into the turn structure so they can be used as one of the two mutually exclusive actions per turn during the Deployment Phase, exactly mirroring the Tactic Card Integration.

## Scope (Narrow)
- Wire the existing Leader ability system into the `TurnManager` so Leader usage respects the "one action per turn" rule.
- Enforce the "one Leader ability per game" limitation.
- Respect the global ability lockout when any player has exhausted.
- Ensure Leader abilities are blocked after player exhaustion and after global exhaustion.

## Why This Task
Leader abilities are a core part of the original Rumble Nation rules (as adapted). With the "one action per turn" enforcement and Tactic integration now complete, we can properly integrate Leader usage as a valid alternative to deployment (or Tactic) on a player's turn while maintaining strict mechanical fidelity.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Leader Ability Integration (Phase 6 Task 3)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Mirror the Tactic Card Integration work exactly for Leader (Flag Ship) abilities.

## Scope (Narrow)
Wire existing Leader abilities into `TurnManager`:
- Leader usage counts as the player's one action for the turn.
- Enforce one-use-per-game.
- Block after player exhaustion and global exhaustion lockout.
- Do not implement new effects or UI — assume the ability execution logic already exists or is handled separately.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 2 - Tactic Card Integration]] (use as exact template)
- Core Mechanics and Deployment Phase Planning notes

## Requirements
- Add `can_player_perform_leader_ability()` style gating in `TurnManager`.
- Update turn action choice logic to include Leader abilities as a valid option (mutually exclusive with Deploy and Tactic).
- Ensure global lockout applies identically to Tactic.
- One Leader ability per game enforcement.

## Acceptance Criteria
- Players can choose Deploy, Tactic, or Leader ability as their single action.
- All exhaustion and one-use rules are respected for Leaders.
- No regression on existing Tactic or deployment flow.
- Clean, well-commented code.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Use the prompt above with Grok Build (or equivalent) to generate the implementation.
2. Update the gap list to mark this task complete once done.
3. Create completion note.

*This keeps the narrow-scope discipline and maintains full rules fidelity.*