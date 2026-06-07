# Stellar Hegemony - Prompt - Task B: Secondary Points Calculation Logic

**Task:** B  
**Part of:** Zone Points System Implementation Plan

---

## Prompt for Grok Build

Create a reusable calculation function for Secondary Points.

**Requirements:**

- Implement a pure function/utility with the signature:
  ```gdscript
  func calculate_secondary_points(primary_points: int) -> int
  ```
- The rule must be: `Secondary Points = round(Primary Points / 2)`
- Examples that must work:
  - 12 → 6
  - 11 → 6
  - 10 → 5
  - 9 → 5
  - 8 → 4
  - 7 → 4
  - 6 → 3
  - 5 → 3
  - 4 → 2
  - 3 → 2
  - 2 → 1

- This function must be the single source of truth for the calculation.
- Add unit tests covering the full range (2–12).

**Success Criteria:**
- The function produces the exact expected values for every input from 2 to 12.
- Tests pass reliably.
- The function is placed in an appropriate utility location following project conventions.

**Scope:** Narrow — only the calculation logic and tests.

---

*Reference: [[Stellar Hegemony - Zone Points System - Implementation Plan]]*
