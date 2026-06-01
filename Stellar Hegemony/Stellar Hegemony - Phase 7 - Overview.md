# Stellar Hegemony - Phase 7 Overview

**Phase Theme:** Game Infrastructure & Shell

**Goal:** Turn the core mechanics (Phase 6) into a playable game with session management, single-player support, and future multiplayer compatibility.

## Phase 7 Guiding Principles
- Must support future multiplayer from the start (player IDs, slots, no single-player assumptions)
- Keep narrow-scope discipline
- Backend logic first, UI/scene flow later
- Slightly smarter AI (not just random)

## Proposed Task Order

| Task | Focus | Goal |
|------|-------|------|
| 7-1 | Game Session Manager (Core) | Create/manage games, register players, leader assignment |
| 7-2 | Player Data & Leader Selection | Proper player state + leader draft flow |
| 7-3 | Single Player Setup | Basic single-player game creation with AI opponent |
| 7-4 | Simple AI Opponent | Rule-based AI that can deploy and use abilities |
| 7-5 | Game Loop Integration | Wire session into actual gameplay flow |
| 7-6 | Polish & State Management | Save/load, better state handling |

This phase focuses on making the game actually runnable as a complete experience.