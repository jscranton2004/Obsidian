# Prompt for Grok Build: Turn Structure

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Turn Structure system that enforces the "one action per turn" rule.

## Key Reference Documents
- `Stellar Hegemony - Turn Structure Design.md`
- `Stellar Hegemony - Deployment Phase Planning.md`
- `Stellar Hegemony - Tactic Card System Planning.md`

## Requirements

### Scope (Narrow)
Focus on enforcing the mutual exclusivity of deployment and tactic usage on a single turn. Do not implement full phase management or War phase yet.

### Core Behavior
- On a player’s turn, they must choose **one** of the following:
  1. Perform a deployment action (roll dice and place units)
  2. Use one available Tactic Card (if eligible)
- These two actions are mutually exclusive.

### Turn Management
- Track whose turn it is.
- Provide a way to start a turn and end a turn.
- Prevent a player from performing both actions on the same turn.

### Eligibility Checks
- A player may only use a Tactic Card if they meet all eligibility requirements (not yet used their one card, can perform the action, global lockout not active).

### Integration Points
- Should work with the existing `DeploymentManager` and `TacticManager`.
- Should respect `PlayerState` (especially `has_used_tactic` and exhaustion status).

## Acceptance Criteria

- A player cannot deploy and use a tactic on the same turn.
- The system correctly prevents invalid action combinations.
- Eligibility for tactic usage is respected.
- The structure is ready to be expanded into a full turn/phase system later.

## Files You Will Likely Touch
- `game/scripts/systems/` (new `turn_manager.gd` or similar recommended)

## Important Notes
- Keep the implementation focused and minimal.
- Build on top of the existing integrated managers.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How turns enforce the one-action rule
- Any assumptions made

This is a narrow-scope task.