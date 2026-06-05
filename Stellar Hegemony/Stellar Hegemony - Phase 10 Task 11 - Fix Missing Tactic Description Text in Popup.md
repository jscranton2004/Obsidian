# Stellar Hegemony - Phase 10 Task 11: Fix Missing Tactic Description Text in Popup

**Status:** Complete (2026-06-05)

## Goal
Ensure every tactic card displays its actual rules/description text in `ActionDetailPopup`.

## Root Cause
Descriptions were looked up only in `TacticManager.get_available_cards()` (the current runtime pool). The pool was created twice — once in `in_game._setup_managers()` and again in `DeploymentPhaseManager.start_deployment_phase()` — so tactic buttons could show cards from the first shuffle while the popup searched the second shuffle. Cards present in both pools (e.g. Reinforce) worked; others showed the placeholder.

## Changes
- `tactic_manager.gd` — added `get_card_definition(card_id)` static lookup against `ALL_TACTIC_CARDS`.
- `deployment_dice_ui.gd` — popup uses canonical definition for title + description; removed `"Tactic card details."` fallback when data exists.
- `in_game.gd` — pool created only in `start_deployment_phase`; refresh tactic buttons after phase start.

## Testing
1. Start a game → Deployment Phase.
2. Hover each tactic card — full rules text for all (Hyperspace Invasion, Sub-Light Squadron, False Flag, etc.).
3. Confirm no popup shows `"Tactic card details."`

*See defect: C:\Defects\2026-06-05 10_32_37 Stellar Hegemony - Godot Engine - missing text.png*