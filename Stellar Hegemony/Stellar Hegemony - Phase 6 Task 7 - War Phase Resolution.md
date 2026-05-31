# Stellar Hegemony - Phase 6 Task 7: War Phase Resolution

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Rules Fidelity Gap List]], [[Stellar Hegemony - Handoff Note - 2026-05-30]]

## Goal
Implement the core War Phase resolution logic so that when the War Phase begins, the game correctly compares unit totals in each zone, determines winners using “most units wins”, and applies exhaustion order as the tiebreaker.

## Scope (Narrow)
- Implement the basic resolution pass in `WarPhaseManager.resolve_war_phase()`.
- For each zone, compare total units between players.
- Apply “most units wins” rule.
- Use exhaustion order as the tiebreaker when totals are equal.
- Do **not** implement ownership updates, scoring, or visual feedback yet — only the resolution decision logic.
- Keep changes minimal and well-commented.

## Why This Task
With the War Phase trigger now working, the next natural narrow step is the actual resolution logic that decides who wins each zone.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: War Phase Resolution (Phase 6 Task 7)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Implement the core War Phase resolution logic (most units wins + exhaustion order tiebreaker).

## Scope (Narrow)
- Add the resolution logic inside `WarPhaseManager.resolve_war_phase()`.
- For every zone, determine the winner using:
  - Highest total units wins.
  - Exhaustion order as tiebreaker when totals are equal.
- Return or store the resolution results (winner per zone).
- Do **not** apply ownership changes or trigger any UI yet.

## Key References
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Handoff Note - 2026-05-30]]
- [[Stellar Hegemony - Phase 6 Task 5 - War Phase Trigger]]
- Exhaustion Order Design and Core Mechanics notes

## Requirements
- Strict adherence to “most units wins” + exhaustion order tiebreaker.
- Clean separation so ownership updates can be added later.
- Well-commented code.

## Acceptance Criteria
- `resolve_war_phase()` correctly identifies winners per zone using the defined rules.
- Exhaustion order is properly used as the tiebreaker.
- No regression on existing phase transition or deployment logic.

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Update gap list upon completion.
3. Create completion note.

*Keeping the narrow-scope discipline and full rules fidelity.*