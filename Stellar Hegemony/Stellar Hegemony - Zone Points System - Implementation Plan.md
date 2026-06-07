# Stellar Hegemony - Zone Points System - Implementation Plan

**Date:** 2026-06-06  
**Status:** Planning  
**Related Gap:** End-of-Game Scoring (Rules Fidelity Gap List #13)

## Overview

We need to implement the **Primary Points** and **Secondary Points** system for zones at the start of the game. This is a foundational requirement for final scoring and must be done with strict fidelity to the original Rumble Nation rules.

### Key Rule Clarification (from original game)
- Every zone has a **Primary Point** value (Large Castle Token equivalent): 2–12
- **Secondary Points** are **not** independently rolled or assigned. They are calculated as:
  - `Secondary Points = round(Primary Points / 2)`
  - Examples:
    - 12 → 6
    - 11 → 6
    - 10 → 5
    - 9 → 5
    - 8 → 4
    - 7 → 4
    - 6 → 3
    - etc.

- These values must be assigned **at game start** when the map is initialized.
- Visual **tokens** (Large and Small) should be attached to zones so players can see the values.

## Goals
- Assign Primary and Secondary point values to all 11 zones when a new game starts.
- Store the values persistently on zone data.
- Create visual token representations attached to zones.
- Break the work into narrow, issue-sized tasks.

## Scope Boundaries
- **In scope:** Data model, initialization logic, visual token attachment.
- **Out of scope:** Actual end-of-game scoring logic, War Phase awarding of tokens, UI for final scoring.

---

## Recommended Task Breakdown (for GitHub Issues)

### Task A: Zone Data Model Extension
**Goal:** Add `primary_points` and `secondary_points` fields to the zone data structure.

**Details:**
- Extend the zone definition (likely in map data or a Zone resource/script) to include two integer fields.
- Ensure these fields are serializable and persist with the zone.
- Add any necessary getters/setters following existing patterns.

**Success Criteria:**
- Zones can store primary and secondary point values.
- Existing zone functionality is unaffected.

---

### Task B: Secondary Points Calculation Logic
**Goal:** Implement the correct calculation rule for Secondary Points.

**Details:**
- Create a pure function/utility: `calculate_secondary_points(primary: int) -> int`
- Rule: `return round(primary / 2.0)`
- This must be the single source of truth for the calculation.

**Success Criteria:**
- The function correctly produces the values listed above (12→6, 11→6, 10→5, etc.).
- Unit tests cover the full range (2–12).

---

### Task C: Zone Points Initialization at Game Start
**Goal:** Assign Primary and Secondary point values to all zones when a `GameSession` is created.

**Details:**
- Determine where map/zone initialization happens during game setup.
- Assign Primary Point values to the 11 zones (distribution method to be defined — either predefined balanced set or procedural with constraints).
- Automatically calculate and assign Secondary Points using the function from Task B.
- Values must be set before the Deployment Phase begins.

**Success Criteria:**
- Every new game starts with all zones having both values assigned.
- Values are visible in the zone data immediately after game creation.

---

### Task D: Visual Token Representation (Large & Small)
**Goal:** Create visual tokens that can be attached to zones showing the point values.

**Details:**
- Design/create two token types (Large Castle Token style and Small Castle Token style) following the 1950s retro space aesthetic.
- Tokens should display the numeric value.
- Attach tokens to zones on the HybridMap so they are visible from game start.
- Tokens should be non-interactive at this stage (visual only).

**Success Criteria:**
- Each zone displays both a Large and Small token with the correct values.
- Visual style matches the established retro/Jetson aesthetic.

---

### Task E: Integration with HybridMap
**Goal:** Wire the new point values and tokens into the existing HybridMap system.

**Details:**
- Ensure the map initialization flow calls the points assignment logic.
- Make sure tokens are instantiated and positioned correctly on each zone mesh.
- Verify that zone data (including points) is accessible from the map layer.

**Success Criteria:**
- When the InGame scene loads, all zones show their point tokens.
- No breakage to existing map functionality.

---

### Task F: Documentation & Rules Fidelity Update
**Goal:** Update relevant documentation to reflect the new system.

**Details:**
- Update the Rules Fidelity Gap List (mark #13 as in progress).
- Add notes about the Secondary Points calculation rule.
- Link this plan to the GameSession and map initialization notes.

---

## Open Questions for Discussion
1. Should Primary Point values be a fixed balanced distribution across the 11 zones, or procedurally generated with constraints?
2. Do we need to support different point distributions for different map variants later?
3. Should token visuals be simple 2D sprites or 3D models at this stage?

---

## Next Steps
Once this plan is reviewed, create individual GitHub issues for Tasks A–F (one issue per task) with this note attached.

*This plan follows the narrow-scope discipline and maintains full rules fidelity.*