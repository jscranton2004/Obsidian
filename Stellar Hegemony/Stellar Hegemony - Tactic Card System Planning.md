# Stellar Hegemony - Tactic Card System Planning

**Status:** Planning / Definition  
**Date:** 2026-05-29  
**Purpose:** Define the rules for how Tactic Cards are selected and used during a game.

## Overview
Tactic Cards provide powerful one-time effects. The system governs how the shared pool of cards is created, how players gain access to them, and the restrictions around their use.

## Card Pool
- There are **12 possible Tactic Cards** (see `Stellar Hegemony - Adapted Tactic Cards.md` for full list and effects).
- At the start of the game, a shared pool of **(number of players + 1)** cards is randomly selected from the 12.
  - 2 players → 3 cards available
  - 3 players → 4 cards available
  - 4 players → 5 cards available
- This pool is visible and available to **all players**.

## Player Restrictions
- Each player may **only ever use 1 Tactic Card** during the entire game.
- A player may only select a card if they are **currently able to perform the action** described on the card.

## Card Usage
- When a player chooses to use a Tactic Card on their turn, they select one from the shared pool.
- After the card’s effect is resolved, the card is **removed** from the pool and cannot be used again by any player.
- Using a Tactic Card ends the player’s turn. They cannot also roll dice to deploy on the same turn.

## Global Lockout
- Once **any player** has placed their last unit, **no player** may use Tactic Cards or Leader abilities for the remainder of the game.

## Turn Structure
On a player’s turn they must choose **one** of the following:
1. Roll dice to deploy units (see Deployment Phase Planning)
2. Select and use one available Tactic Card (if eligible)

These two actions are mutually exclusive.

## Scope Notes
This planning note focuses on the **selection and availability** rules for Tactic Cards. The following are out of scope for this document:
- Implementation of the actual card effects
- UI for displaying and selecting cards
- Leader card usage (covered separately)

## References
- `Stellar Hegemony - Adapted Tactic Cards.md` — Full list of 12 cards and their effects
- `Stellar Hegemony - Core Mechanics.md` — High-level mention of Tactic Cards
- `Stellar Hegemony - Deployment Phase Planning.md` — Related turn structure and lockout rules

---

*This document exists to clearly define the Tactic Card availability and usage rules.*