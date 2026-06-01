# Stellar Hegemony - Phase 7 Task 6: Polish & State Management

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 7 - Overview]], [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]]

## Goal
Polish the `GameSession` system and add flexible player composition support, particularly for single-player games with multiple AI opponents (up to 3 bots, max 4 total players).

## Scope (Narrow)
- Enhance `GameSession` / single-player helpers to support flexible player mixes:
  - 1 human + up to 3 AI bots
  - Mixtures such as 1 local + 1 remote + 2 bots, etc.
- Enforce the hard cap of 4 players total
- Improve any state management or helper methods as needed
- Keep everything multiplayer-friendly

## Why This Task
The current single-player helper only supports 1 human + 1 AI. Players want more flexible compositions (especially more AI opponents). This is a natural polish item before closing Phase 7.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Polish & State Management (Phase 7 Task 6)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Improve `GameSession` flexibility for single-player and mixed player compositions.

## Scope (Narrow)
- Support up to 3 AI opponents in single-player games (max 4 players total)
- Allow flexible mixes (e.g. 1 local + 1 remote + 2 bots)
- Enforce the 4-player hard cap
- Improve any related state or helper methods
- Keep multiplayer-friendly design

## Key References
- [[Stellar Hegemony - Phase 7 - Overview]]
- [[Stellar Hegemony - Phase 7 Task 3 - Single Player Setup]]

## Requirements
- `create_single_player_session` style helpers should support 1–3 AI opponents
- Clear validation when exceeding 4 players
- Clean, documented API

## Acceptance Criteria
- Can create sessions with 1 human + 1–3 AI players
- Flexible player type combinations are supported
- 4-player limit is enforced
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Close Phase 7 once complete.

*Keeping the narrow-scope discipline.*