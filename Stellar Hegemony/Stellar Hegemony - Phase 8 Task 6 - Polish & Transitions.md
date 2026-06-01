# Stellar Hegemony - Phase 8 Task 6: Polish & Transitions

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]], [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]], [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]], [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]]

## Goal
Add basic polish to the menu flow: simple scene transition effects and a lightweight loading screen.

## Scope (Narrow)
- Add a simple fade transition between scenes using SceneManager
- Create a minimal LoadingScreen scene that can be shown during transitions
- Apply the fade effect on all existing menu transitions (Main Menu ↔ Game Setup ↔ Settings ↔ In-Game)
- Keep effects lightweight (no complex animations or particles)
- Do not add new menu options or change existing functionality

## Why This Task
Phase 8 is now functionally complete. This final task adds a thin layer of polish so the menu flow feels smoother without expanding scope.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Polish & Transitions (Phase 8 Task 6)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Add basic polish to the menu flow with simple scene transitions and a loading screen.

## Scope (Narrow)
- Add a simple fade transition between scenes using SceneManager
- Create a minimal LoadingScreen scene that can be shown during transitions
- Apply the fade effect on all existing menu transitions (Main Menu ↔ Game Setup ↔ Settings ↔ In-Game)
- Keep effects lightweight (no complex animations or particles)
- Do not add new menu options or change existing functionality

## Key References
- [[Stellar Hegemony - Phase 8 - Overview]]
- [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]]
- [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]]
- [[Stellar Hegemony - Phase 8 Task 3 - Game Setup Screen]]
- [[Stellar Hegemony - Phase 8 Task 5 - Settings Menu]]

## Requirements
- SceneManager supports a fade transition
- A basic LoadingScreen exists and can be shown during longer transitions
- All menu transitions use the new fade effect
- Code remains minimal and clean

## Acceptance Criteria
- Transitions between menus feel smoother with a fade
- LoadingScreen appears during transitions when appropriate
- No existing functionality is broken
- All previous Phase 8 tests still pass
- Well-commented code

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Phase 8 complete — move to Phase 9 planning once finished.

*Keeping the narrow-scope discipline.*