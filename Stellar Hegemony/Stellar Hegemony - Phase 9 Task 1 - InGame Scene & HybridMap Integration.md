# Stellar Hegemony - Phase 9 Task 1: InGame Scene & HybridMap Integration

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Phase 9 - Summary]], [[Stellar Hegemony - HybridMap Base Layer - Implementation Notes]]

## Goal
Create a proper `InGame.tscn` scene that instantiates the `HybridMap`, wires up the existing HUD, and makes the Deployment phase visually visible and interactive instead of a black screen.

## Scope (Narrow)
- Create `scenes/levels/InGame.tscn`
- Instance `HybridMap.tscn` as a child
- Add the existing HUD elements (ActionHintLabel, phase labels, player/leader display) from the Phase 9 work
- Ensure the scene receives the `GameSession` from `SceneManager`
- Keep the implementation minimal — do not rewrite Deployment logic or add new visuals yet
- Make sure the scene loads without errors and displays the nebula plane + zones

## Why This Task
Even though all systems initialise correctly, the game currently shows a black screen because `InGame.tscn` does not exist. This task is the critical missing piece that makes the Deployment phase actually visible to the player.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: InGame Scene & HybridMap Integration (Phase 9 Task 1)

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Create the missing `InGame.tscn` so the game no longer shows a black screen after Leader Selection.

## Scope (Narrow)
- Create `scenes/levels/InGame.tscn`
- Instance `HybridMap.tscn` as a child node
- Include the HUD elements created during Phase 9 (phase labels, ActionHintLabel, player/leader display)
- Wire the scene to receive the GameSession passed by SceneManager
- Ensure the scene loads cleanly and displays the nebula plane + zones

## Key References
- [[Stellar Hegemony - Phase 9 - Summary]]
- [[Stellar Hegemony - HybridMap Base Layer - Implementation Notes]]
- [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

## Requirements
- The scene must load without errors when transitioning from Leader Selection
- HybridMap must be visible (nebula plane + zones)
- Existing HUD from Phase 9 must be present
- No changes to core game logic (DeploymentManager, TurnManager, etc.)

## Acceptance Criteria
- Game transitions from Leader Selection into a visible InGame scene
- Player can see the map and HUD instead of a black screen
- All existing Phase 9 flow continues to work

Please implement this cleanly. After completion, briefly describe what was created, how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build.
2. Test the full flow after delivery.
3. Create completion note once verified.

*Keeping the narrow-scope discipline.*