# Stellar Hegemony - Prompt - Task E: HybridMap Integration

**Task:** E  
**Part of:** Zone Points System Implementation Plan

---

## Prompt for Grok Build

Attach the visual point tokens to the existing zones on the HybridMap, using the values assigned during game initialization.

**Requirements:**

- The HybridMap already contains exactly 11 zones. Do **not** create, remove, or modify any zones.
- For each of the 11 existing zones:
  - Attach the **Large token** displaying the **Primary Point** value that was randomly assigned to that zone in Task C.
  - Attach the **Small token** displaying the **Secondary Point** value, which must be calculated from the zone’s Primary Point value using the function from Task B.
- The tokens must reflect the actual values that were assigned during `GameSession` creation.
- The map layout, zone count, and zone connectivity must remain completely unchanged.

**Success Criteria:**
- All 11 existing zones correctly display both their Large (Primary) and Small (Secondary) point tokens.
- Primary tokens show the randomly assigned unique values from the array `[2..12]`.
- Secondary tokens correctly show the calculated values (`round(Primary / 2)`).
- No changes are made to the number or structure of zones.
- Existing HybridMap functionality continues to work without modification.

**Scope:** Very narrow — only the attachment of tokens to the current zones using the values from Task C. Do not alter map structure.

---

*Reference: [[Stellar Hegemony - Zone Points System - Implementation Plan]]*