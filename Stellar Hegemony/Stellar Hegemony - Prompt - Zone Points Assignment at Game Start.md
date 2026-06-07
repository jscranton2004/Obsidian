# Stellar Hegemony - Prompt - Zone Points Assignment at Game Start

**Date:** 2026-06-06  
**Purpose:** Detailed prompt for implementing Primary Points and Secondary Points assignment during game setup.

---

## Prompt (Ready to Paste)

You are implementing a critical rules-fidelity feature for Stellar Hegemony (a digital adaptation of Rumble Nation).

**Requirement:** At the very start of a new game, every zone on the map must be assigned two permanent values:
- **Primary Points** (equivalent to the Large Castle Token) — values range from 2–12
- **Secondary Points** (equivalent to the Small Castle Token) — values range from 1–6

These values must be assigned when the `GameSession` is created during the setup flow, and they must persist for the entire game. They are used for final scoring at the end of the game (highest total Primary Points wins, with Secondary Points as tiebreakers where relevant).

**Strict Rules Fidelity Requirements:**
- The values must follow the original Rumble Nation distribution logic (or a balanced equivalent that matches the spirit of the board game).
- Each zone must have both values assigned from the beginning — they are not awarded during the War Phase in this implementation. They are fixed properties of the zone.
- The values must be stored on the zone data model so they are accessible to:
  - The HybridMap / zone rendering system (so they can eventually be displayed)
  - The future scoring system
  - Any UI that shows zone information
- Do **not** implement end-of-game scoring yet. Only implement the assignment of these two values at game start.
- Maintain narrow scope: only handle the assignment of Primary and Secondary point values during game initialization.

**Implementation Guidance:**
- Extend the zone data structure (likely in the map or zone definition) to include `primary_points` and `secondary_points`.
- Modify the game setup / `GameSession` creation logic so these values are assigned when a new game begins.
- Ensure the values are set before the Deployment Phase starts.
- The assignment should happen in one clear location (probably in the `GameSession` or a dedicated `MapSetup` / `ZoneInitializer` helper).
- Keep all existing narrow-scope discipline and rules fidelity standards.

**Success Criteria:**
- When a new game starts, every zone has both a Primary Points and Secondary Points value assigned.
- These values are stored persistently on the zone objects for the duration of the game.
- No other gameplay systems are affected.
- The change is minimal and focused only on initialization.

Write the implementation in the correct location following the existing code patterns in the project.

---

## Related Notes
- [[Rumble Nation - Rules Overview]]
- [[Stellar Hegemony - Rules Fidelity Gap List]]
- [[Stellar Hegemony - Unit Representation Planning]]

---

*This prompt was prepared for use with Grok Build.*