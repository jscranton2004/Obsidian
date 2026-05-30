# Stellar Hegemony - Game Identity & Rules Clarification

**Purpose:** This document exists to prevent misinterpretation of the game's core identity and rules.

## Core Identity

Stellar Hegemony is **not** a traditional 4X or area-control strategy game with combat sequences.

It is a **dice-driven area control game** with two distinct phases:

1. **Deployment Phase** — Players roll dice to place units into zones.
2. **War Phase** — After all players have finished deploying, zones are resolved.

## Critical Rules (Do Not Misinterpret)

- There is **no movement during the War Phase**.
- There are **no cards played during the War Phase**.
- There are **no combat sequences** (no attacking, defending, rounds, etc.).
- The War Phase is a **pure resolution step**:
  - The player with the **most units** in a zone gains control.
  - Ties are broken by **exhaustion order** (the order in which players ran out of units).
- Movement only happens **outside** the War Phase (during a player's turn in the Deployment Phase).

## Why This Matters

Many strategy games use "move + fight" loops. Stellar Hegemony deliberately avoids this. The tension comes from:
- Dice placement decisions
- Unit conservation
- Exhaustion order as a tiebreaker

Any prompt or implementation that introduces "combat sequences", "War movement", or "cards during War" is incorrect and should be rejected.

## Usage

This note should be referenced in all future prompts involving the War Phase, movement, or combat to ensure correct interpretation.