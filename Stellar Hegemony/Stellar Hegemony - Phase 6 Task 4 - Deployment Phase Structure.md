# Stellar Hegemony - Phase 6 Task 4: Deployment Phase Structure

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Implement the proper Deployment Phase loop so the game correctly handles turn order, action choice (Deploy / Tactic / Leader), exhaustion detection, and phase transition to War Phase.

## Scope (Narrow)
- Create / wire a `DeploymentPhaseManager` (or extend `TurnManager`) that orchestrates the full Deployment Phase.
- Enforce the one-action-per-turn choice for every player in sequence.
- Detect when all players have exhausted (via the existing exhaustion system) and automatically trigger the end of the Deployment Phase.
- Maintain strict one-action rule across Deploy, Tactic, and Leader abilities.
- Do not implement War Phase resolution logic yet — only the structure and transition.

## Why This Task
With one-action enforcement + Tactic + Leader integration complete, the Deployment Phase now needs a proper orchestrator so the game can run a full round without manual intervention. This is the next logical narrow step before War Phase work.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Deployment Phase Structure (Phase 6 Task 4)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Build the Deployment Phase orchestration layer so the game can run a full deployment round with proper turn order and automatic phase transition.

## Scope (Narrow)
- Implement a `DeploymentPhaseManager` (or extend existing managers) that:
  - Handles player turn order during Deployment.
  - Presents the three action choices (Deploy units, Use Tactic, Use Leader ability).
  - Enforces exactly one action per turn using the existing `can_*` / `perform_*` gates.
  - Detects when all players have exhausted and ends the Deployment Phase.
- Do **not** implement War Phase resolution or ownership changes yet.
- Reuse all existing exhaustion, one-use, and global lockout logic.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 3 - Leader Ability Integration]] (just completed)
- [[Stellar Hegemony - Phase 6 Task 2 - Tactic Card Integration]]
- Deployment Phase Planning and Exhaustion Order Design notes

## Requirements
- Clear turn sequencing for 2–4 players.
- Action choice must respect the one-action rule (Deploy OR Tactic OR Leader).
- Automatic detection of "all players exhausted" → end Deployment Phase.
- Clean separation so War Phase can be wired in later.

## Acceptance Criteria
- A full Deployment Phase can be run from start to exhaustion without manual intervention.
- All three action types are properly gated.
- When the last player exhausts, the phase ends cleanly.
- No regression on existing Leader/Tactic/Deploy flows.
- Well-commented code with explicit Phase 6 Task 4 references.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*