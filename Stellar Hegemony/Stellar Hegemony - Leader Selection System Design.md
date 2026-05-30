# Stellar Hegemony - Leader Selection System Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define how leaders are selected at the start of each game.

## Overview

At the beginning of every game, players must select their Legendary Commander (Leader). The selection process uses reverse turn order and always excludes one leader when there are fewer than 5 players.

## Core Rules

### The Six Leaders
There are exactly 6 possible leaders:

- **Commander Skitter** (Ant-men) – *The Swarm Lord*
- **Admiral Vance "Ironjaw" Hale** (Human) – *The Last Terran*
- **High Lord Glubthar** (Fish-men) – *Voice of the Abyssal Current*
- **Sky Marshal Quill** (Bird-men) – *The Stormfeather*
- **Lord Granite** (Rock-men) – *The Unmoving*
- **The Many** (Weird Blobs) – *The Thousand-Minded*

### Selection Process
- Number of leaders offered = **number of players + 1**
- One leader is always randomly excluded when there are 2–4 players
- Turn order is determined at the start of the game
- Players pick leaders in **reverse turn order** (the player who goes last picks first)
- Once chosen, a leader is removed from the pool

### Turn Order
- Turn order is established randomly at the start of each game.
- The last player in the turn order always selects their leader first.

## Scope for Implementation

- Create a `LeaderManager` (or similar) that can be called at game start.
- Handle random leader pool generation.
- Handle random turn order generation.
- Support the reverse-order picking sequence.
- Do **not** implement leader abilities, UI, or player assignment yet.

## Integration Points

- Should be callable early in the game setup flow.
- Should eventually feed into `PlayerState` (once leaders are assigned).
- Should work with the existing `TurnManager`.

## References

- `Stellar Hegemony - Core Mechanics.md`
- `Stellar Hegemony - Adapted Flag Ship Cards.md`
- `Stellar Hegemony - Prompt - Leader Selection System.md`

---

*This system establishes both turn order and leader ownership at the very start of the game.*