# Stellar Hegemony - Prompt - Task A: Zone Data Model Extension

**Task:** A  
**Part of:** Zone Points System Implementation Plan

---

## Prompt for Grok Build

Extend the zone data model to support Primary and Secondary point values.

**Requirements:**

- Add two new integer fields to the zone data structure:
  - `primary_points` (values 2–12)
  - `secondary_points` (calculated value)

- Follow the existing patterns used for other zone properties in the codebase.
- Ensure the fields are properly initialized (default to 0 or null until assigned).
- Make sure the data is serializable and will persist correctly with the zone.

**Success Criteria:**
- Every zone object can store both `primary_points` and `secondary_points`.
- No existing zone functionality is broken.
- The new fields follow the project's current data model conventions.

**Scope:** Narrow — only the data model change. Do not implement assignment logic or visuals yet.

---

*Reference: [[Stellar Hegemony - Zone Points System - Implementation Plan]]*
