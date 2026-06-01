# Stellar Hegemony - Phase 8 Task 5: Settings Menu

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 8 - Overview]], [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]], [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]]

## Goal
Create a basic Settings menu screen with a few simple configurable options.

## Scope (Narrow)
- Create a simple `Settings` scene
- Options to include:
  - Master volume slider (or mute toggle as a minimal version)
  - Fullscreen toggle
  - Back to Main Menu button
- Use `SceneManager` for transitions
- Keep UI minimal and clean (plain Godot nodes)
- Persist settings using Godot’s built-in `ConfigFile` or `ProjectSettings` (no custom save system yet)

## Why This Task
The menu system is now functional. Adding a basic Settings screen completes the core menu loop (Main Menu → Settings → back) and gives players control over basic quality-of-life options before we move on.

## Ready-to-Use Prompt for Grok Build
```
# Prompt for Grok Build: Settings Menu (Phase 8 Task 5)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create a basic Settings menu screen.

## Scope (Narrow)
- Simple Settings scene with UI elements
- Options:
  - Master volume slider (or mute toggle)
  - Fullscreen toggle
  - Back to Main Menu button
- Use SceneManager for transitions
- Minimal, clean UI (no heavy styling)
- Persist settings using Godot’s built-in ConfigFile or ProjectSettings

## Key References
- [[Stellar Hegemony - Phase 8 - Overview]]
- [[Stellar Hegemony - Phase 8 Task 1 - Scene Manager]]
- [[Stellar Hegemony - Phase 8 Task 2 - Main Menu]]

## Requirements
- Functional settings screen reachable from Main Menu
- Volume and fullscreen options work and persist
- Proper transitions via SceneManager
- Easy to extend later

## Acceptance Criteria
- Settings scene loads correctly from Main Menu
- Volume and fullscreen controls function
- Changes persist between sessions
- Back button returns cleanly to Main Menu
- Well-commented code and scene

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Create completion note after delivery.
3. Move to Task 6 (Polish & Transitions) once complete.

*Keeping the narrow-scope discipline.*