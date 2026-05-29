# Prompt for Grok Build: Reserves System (Corrected Model)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Reserves system using the correct model: each player has a **single pool of 18 fleets total**. Reserves represent the **undeployed portion** of that pool.

## Key Reference Documents
- `Stellar Hegemony - Reserves System Design.md` (revised)
- `Stellar Hegemony - Adapted Tactic Cards.md`
- `Stellar Hegemony - PlayerState - Implementation Notes.md`

## Problem with Previous Implementation
The prior version treated reserves as a separate pool. This is incorrect. Reserves should simply be the fleets that have **not yet been placed** on the board (starting at 18).

## Requirements

### Core Model (Single Pool)
- Each player has **18 fleets total**.
- `reserves` = `18 - fleets_currently_on_board`.
- When a player deploys, they move fleets **from reserves to the board**.
- When a player uses **Emergency Withdrawal**, fleets move **from the board back to reserves**.
- Exhaustion only occurs when the **entire 18-unit pool** is gone (board + reserves = 0).

### Required Changes
- Update `PlayerState` to track total fleets (18) and currently deployed fleets.
- Provide clean methods:
  - `deploy_from_reserves(player_id, amount)`
  - `return_to_reserves(player_id, amount)`
  - `get_reserves(player_id)` (calculated or stored)
- Update `CardEffectExecutor` to support the three relevant cards using this model:
  - **Reinforce**
  - **Insurrection**
  - **Emergency Withdrawal**

### Scope
- Keep changes minimal.
- Do **not** add custom game setup or variable starting values.
- Do **not** implement full War phase logic.

## Acceptance Criteria
- Players start with 18 fleets in reserves.
- Deploying reduces reserves.
- Returning units to reserves increases reserves.
- Exhaustion is only triggered when total fleets reach zero.
- The three tactic cards that reference reserves function correctly.

## Files You Will Likely Touch
- `game/scripts/systems/player_state.gd`
- `game/scripts/systems/card_effect_executor.gd`

## Important Notes
- This is a corrective implementation of the proper single-pool reserves model.
- Keep the implementation focused and minimal.

Please implement this cleanly with good comments. After completion, briefly describe:
- How the single 18-unit pool model is implemented
- How reserves are calculated/tracked
- Confirmation that the three relevant cards are supported

This is a narrow-scope task.