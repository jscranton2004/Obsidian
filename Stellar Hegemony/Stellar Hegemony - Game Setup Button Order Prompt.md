# Stellar Hegemony - Game Setup Button Order Prompt

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]]

## Goal
Swap the order of the two buttons on the Game Setup screen so that **"Continue to Leader Selection"** appears above **"Back to Main Menu"** (more natural flow: primary action first, then back).

## Scope (Narrow)
- Reorder the two Button nodes inside `GameSetup.tscn`.
- No changes to scripts, logic, or any other UI elements.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Game Setup Button Order

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)

## Goal
On the Game Setup screen, "Continue to Leader Selection" should appear above "Back to Main Menu" (primary action first).

## Scope (Narrow — do ONLY this)
In `game/scenes/ui/GameSetup.tscn`, reorder the two Button children so that:

1. Continue to Leader Selection
2. Back to Main Menu

(They are currently in the reverse order.)

Do not change any text, signals, scripts, or other nodes.

## Acceptance Criteria
- When the Game Setup scene is opened, the button order is:
  - Continue to Leader Selection (top)
  - Back to Main Menu (bottom)

Please make this small UI ordering change.
```

## Next Actions
1. Send the prompt to Grok Build.
2. Verify the button order in the editor or at runtime.
3. Create completion note when done.

*Keeping the narrow-scope discipline.*