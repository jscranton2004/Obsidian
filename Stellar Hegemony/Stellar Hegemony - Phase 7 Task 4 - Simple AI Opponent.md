# Stellar Hegemony - Phase 7 Task 4: Simple AI Opponent

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]], [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]]

## Goal
Create a basic AI opponent that can participate in a single-player game by making deployment decisions.

## Scope (Narrow)
- Create a simple `SimpleAI` or `AIOpponent` class
- The AI should be able to:
  - Choose a zone to deploy into
  - Choose how many units to deploy (basic heuristics)
  - Optionally decide whether to include its Flag Ship
- Keep the AI "slightly smarter" than pure random (e.g. prefers zones with good connectivity or value)
- No advanced tactics or leader ability usage yet
- Must work with the existing `GameSession` and `DeploymentManager`

## Why This Task
With single-player session creation now possible, adding basic AI behavior will allow us to actually play a full single-player game.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Simple AI Opponent (Phase 7 Task 4)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create a basic AI opponent that can make deployment decisions in a single-player game.

## Scope (Narrow)
- New simple AI class
- Can choose deployment zone and unit count
- Slightly smarter than random (basic heuristics)
- Works with existing GameSession and DeploymentManager
- No leader abilities or advanced tactics yet

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]]

## Requirements
- AI should be able to participate in the deployment phase
- Keep logic simple and readable
- Multiplayer-friendly design (AI is just another player)

## Acceptance Criteria
- AI can make reasonable deployment choices
- Can be wired into a single-player game session
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 5 once complete.

*Keeping the narrow-scope discipline.*