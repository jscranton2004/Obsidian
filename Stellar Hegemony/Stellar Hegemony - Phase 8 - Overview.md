# Stellar Hegemony - Phase 8 Overview

**Phase Theme:** Main Menu & Scene Flow

**Goal:** Build the user-facing shell of the game — menus, scene transitions, and game flow — now that the core systems and single-player infrastructure are stable.

## Phase 8 Guiding Principles
- Menus should be informed by what the underlying systems actually need (hence doing this after Phase 7)
- Keep UI and scene logic separate from game logic
- Support both single-player and future multiplayer flows
- Maintain the narrow-scope discipline

## Proposed Task Order (Initial)

| Task | Focus | Goal |
|------|-------|------|
| 8-1 | Scene Manager / Game State Machine | Central system for changing scenes and tracking game state |
| 8-2 | Main Menu | Basic main menu with options to start single-player, multiplayer (future), settings, quit |
| 8-3 | Game Setup Screen | Leader selection, player setup, AI count selection |
| 8-4 | In-Game HUD / Flow | Connecting the existing game loop to the UI |
| 8-5 | Settings Menu | Basic configurable options (volume, etc.) |
| 8-6 | Polish & Transitions | Scene transition effects, loading screens, overall flow polish |

This phase shifts focus from backend systems to the actual player experience.