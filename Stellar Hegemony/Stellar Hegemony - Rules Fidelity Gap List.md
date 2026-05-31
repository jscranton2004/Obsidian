# Stellar Hegemony - Rules Fidelity Gap List

**Purpose:** This document tracks gaps between the current implementation and the original Rumble Nation rules (as adapted in the Stellar Hegemony design docs). The goal is to ensure the digital version functions identically to the board game.

**Last Updated:** 2026-05-30

---

## Priority Legend

| Priority | Meaning |
|----------|---------|
| **High** | Core rule is missing or broken. Blocks proper gameplay. |
| **Medium** | Important rule is incomplete or not enforced. |
| **Low** | Nice-to-have or edge case that can be addressed later. |

---

## High Priority Gaps

| # | Gap | Description | Related Documents |
|---|-----|-------------|-------------------|
| 1 | **One Action Per Turn Enforcement** | Players must choose either "Deploy units" or "Use one Tactic/Leader ability" per turn. Currently not enforced. | Turn Structure Design |
| 2 | **Tactic Card Integration** | ~~Tactic cards must be usable once per game and locked out after exhaustion. Not wired into the turn system.~~ **COMPLETED** 2026-05-30 | Turn Structure Design, Deployment Phase Planning |
|| 3 | **Leader Ability Integration** | ~~Leader abilities must respect exhaustion lockout and one-use-per-game rules. Currently disconnected.~~ **COMPLETED** 2026-05-31 | Deployment Phase Planning, Core Mechanics |
| 4 | **Deployment Phase Structure** | The game needs a proper Deployment Phase loop with turn order, action choice, and phase end detection. | Deployment Phase Planning |
| 5 | **War Phase Trigger** | The game must automatically detect when all players have exhausted and trigger the War Phase. Currently manual. | Core Mechanics, Exhaustion Order Design |
| 6 | **Global Ability Lockout** | Once any player exhausts, all players lose access to Tactic and Leader abilities. Not implemented. | Deployment Phase Planning |
| 7 | **Exact Deployment Rules** | Several edge cases are missing:<br>• Choosing which die determines quantity<br>• Flag Ship placement restrictions<br>• "Place exact amount or as many as remain"<br>• Low-token scenarios | Deployment Phase Planning |

---

## Medium Priority Gaps

| # | Gap | Description | Related Documents |
|---|-----|-------------|-------------------|
| 8 | **Exhaustion Order Application** | Exhaustion order is tracked but not yet used as the tiebreaker during War Phase resolution in all cases. | Exhaustion Order Design |
| 9 | **Flag Ship Rules** | A player may only have one Flag Ship on the map at a time. Not enforced. | Deployment Phase Planning |
| 10 | **Deployment Phase End Condition** | No system yet detects when all players have exhausted and ends the Deployment Phase. | Deployment Phase Planning |
| 11 | **Tactic Card Eligibility** | Rules around when a Tactic can be played (global lockout, one-use, etc.) are not enforced. | Turn Structure Design |

---

## Low Priority Gaps

| # | Gap | Description | Related Documents |
|---|-----|-------------|-------------------|
| 12 | **Reinforcement / Wormhole Movement** | The original game allows sending reinforcements through wormholes during War Phase. Not yet designed. | Core Mechanics |
| 13 | **End-of-Game Scoring** | Zone values (2–12) are used for final scoring. Not implemented. | Core Mechanics |
| 14 | **Full Tactic & Leader Card Library** | Only a subset of cards/effects are implemented. | Rumble Nation - Tactic Cards, Daimyo Leader Cards |

---

## Summary

| Priority | Count |
|----------|-------|
| High     | 7     |
| Medium   | 4     |
| Low      | 3     |

**Top 3 Immediate Priorities:**
1. One Action Per Turn enforcement
2. Tactic + Leader ability integration into turns
3. Proper Deployment Phase structure + War Phase trigger

---

*This list should be used to guide future development tasks to ensure the digital version stays faithful to the original board game rules.*