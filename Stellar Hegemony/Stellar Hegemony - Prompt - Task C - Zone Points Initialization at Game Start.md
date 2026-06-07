# Stellar Hegemony - Prompt - Task C: Zone Points Initialization at Game Start

**Task:** C  
**Part of:** Zone Points System Implementation Plan

---

## Prompt for Grok Build

Implement the logic that assigns Primary and Secondary point values to all zones when a new game starts.

**Requirements:**

- When a `GameSession` is created (during game setup), assign values to all 11 zones.
- Primary Point values must be assigned to each zone (use a balanced distribution across the 11 zones — define a reasonable fixed set for now).
- Secondary Points must be calculated automatically using the function from Task B.
- Values must be written to the zone data before the Deployment Phase begins.
- The initialization should happen in one clear, central location (likely near `GameSession` creation or a dedicated map initializer).

**Success Criteria:**
- Every new game starts with all zones having both Primary and Secondary point values assigned.
- Secondary Points are always derived from Primary Points using the correct rule.
- Values are available immediately after game creation.

**Scope:** Narrow — only the initialization logic at game start. Do not create visuals yet.

---

*Reference: [[Stellar Hegemony - Zone Points System - Implementation Plan]]*
