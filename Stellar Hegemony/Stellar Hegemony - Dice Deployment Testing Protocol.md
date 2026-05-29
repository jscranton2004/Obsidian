# Stellar Hegemony - Dice Deployment Testing Protocol

**Status:** Official — 2026-05-29  
**Related:** Dice Deployment UI Implementation Plan (now complete)

## Delivered Implementation Summary

**New Reusable Components**
- `scenes/ui/DiceDisplay.tscn` + `scripts/ui/dice_display.gd`
  - Real dice assets (`Dice_1.png` … `Dice_6.png`)
  - Distinct visual states: warm gold "UNITS" vs cool cyan "SECTOR"

**Main Controller**
- `scenes/ui/DeploymentDiceUI.tscn` + `scripts/ui/deployment_dice_ui.gd`
  - Roll button, live Sector Sum, Units Die indicator
  - Selection model: click to choose the Units die (other two become Sector pair — always valid)
  - Emits `dice_selection_confirmed(sector_sum, unit_value)`

**Integration**
- `scenes/levels/Main.tscn` now uses the new UI (placeholder replaced)

## Official Testing Protocol

**Steps to verify the narrow-scope feature:**

1. Open `scenes/levels/Main.tscn`
2. Run scene (F5)
3. Click **Roll 3 Dice** — confirm three real dice images appear
4. Click any die:
   - It becomes the Units die (gold badge)
   - Other two become Sector pair (cyan badges)
   - Sector Sum updates correctly and live
5. Re-roll and re-select freely
6. Confirm button enables and emits signal (check console output)

**Acceptance Criteria**
- Only existing dice assets used
- Selection always produces exactly 1 unit die + 2 sector dice
- No leakage into map/reserves systems
- Follows naming and signal conventions

**Future Hook**
Wire `dice_selection_confirmed` signal when implementing zone targeting.

---

*This protocol should be referenced in all future dice-related work and milestone reviews.*