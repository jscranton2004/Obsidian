# Stellar Hegemony - Video Resolution & Settings Options

**Status:** Planning → Implementation
**Priority:** Medium (improves testing & accessibility)
**Related:** Phase 8 Settings Menu (already exists), Main Menu

## Goal
Allow players to select different screen resolutions and toggle between Fullscreen / Windowed mode. The 3D map background should scale with the window size, while most 2D UI elements (dice, leader panels, reserves, tactic cards, etc.) remain at their current fixed pixel size.

Current behavior: Game is locked at 1152×648 (Steam Deck optimized).

## Requirements
- Add resolution selection to the existing Settings menu.
- Support common resolutions (e.g. 1280×720, 1920×1080, 2560×1440, and possibly custom).
- Fullscreen / Windowed / Borderless Windowed options.
- UI elements should **not** scale up with resolution (fixed pixel size).
- The 3D map view (HybridMap) should take advantage of larger screen real estate.
- Settings must persist across sessions.
- Changes should apply live where possible (or require a confirmation/apply button).

## Proposed Implementation Steps (Narrow Scope)

### Step 1: Extend SettingsMenu UI
- Add a `Resolution` OptionButton / Dropdown with common resolutions.
- Add a `Window Mode` OptionButton (Fullscreen, Windowed, Borderless).
- Add an "Apply" button (recommended for resolution changes to avoid jarring live switches).
- Keep existing volume and fullscreen controls.

### Step 2: Create Resolution Handling Logic
- Create a new autoload or extend `SettingsMenu` with static methods:
  - `get_available_resolutions()`
  - `apply_resolution(width, height, fullscreen)`
  - `load_and_apply_video_settings()`
- Use `DisplayServer.window_set_size()` and `DisplayServer.window_set_mode()`.
- Decide on content scaling strategy:
  - Keep most Control nodes at `Layout > Transform > Scale = (1,1)` (fixed pixel size).
  - Allow the main 3D viewport / SubViewportContainer for the map to expand.

### Step 3: Handle UI vs Map Scaling
- Identify which nodes should stay fixed size vs which should scale.
- HybridMap and the 3D camera/viewport should respond to window size changes.
- Most UI panels (DeploymentDiceUI, TacticLeaderUI, ReservesUI, etc.) should remain at current design size.

### Step 4: Persistence
- Extend the existing `user://settings.cfg` (already used by SettingsMenu).
- Add keys: `resolution_width`, `resolution_height`, `window_mode`.
- Load and apply video settings early in `main.gd` (before showing Main Menu).

### Step 5: Integration & Polish
- Wire the new options into the existing Settings scene.
- Add a "Restart required" note if some changes need a scene reload.
- Update the Settings test file if needed.
- Ensure the settings work in both editor and exported builds.

## Open Questions
- Should we support custom resolutions or only a curated list?
- Do we want an "Apply" + "Cancel" flow, or live preview?
- Should the map always be letterboxed/pillarboxed or stretch to fill?

## Next Actions
- Create GitHub issues for each narrow-scope step above.
- Implement Step 1 first (UI), then Step 2 (logic).

**Recorded:** 2026-06-10 by Hermes (Ron) based on user request.