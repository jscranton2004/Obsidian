# Stellar Hegemony - Phase 1 Task 2: Basic End-of-Turn Flow

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 1 Integration Plan]]

## Goal
Add a simple end-of-turn system so the game has a basic playable loop (Deployment → End Turn → Next turn).

## Scope (Narrow)
- Add an "End Turn" action/button
- Reset any pending deployment state
- Advance to the next player using the existing `TurnManager`
- Prepare the state for the next deployment phase
- Keep it minimal — no full scoring or complex rules yet

## Why This Task
After dice deployment is working, the next natural step is giving the player a way to finish their turn. This creates the first real gameplay loop.