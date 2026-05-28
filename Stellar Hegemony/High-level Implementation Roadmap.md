# High-level Implementation Roadmap

**Last Updated:** 2026-05-28  
**Status:** Draft

## Vision

A 1950s retro space strategy game in the spirit of classic area-control board games, rethemed around interstellar empires, wormholes, and fleet command.

## Core Pillars

- **Hybrid Map System** (procedural nebula base + individual zone meshes)
- **6 Playable Factions** with unique leaders
- **Card-driven gameplay** (Leaders + Tactics)
- **Strong retro visual identity** (Atompunk / Jetson aesthetic)

## High-Level Phases

### Phase 1: Foundation (Current Focus)

- [x] Project structure & Godot setup
- [x] Asset pipeline (leader cards, tactic cards, dice)
- [x] Hybrid map architecture decision
- [ ] Clickable territory prototype (Milestone 1)
- [ ] Basic zone ownership system
- [ ] Camera controls for the map

### Phase 2: Core Gameplay Loop

- Faction selection & leader placement
- Basic fleet movement (hyperspace + wormholes)
- Zone control & point scoring
- Simple combat resolution
- End-of-turn structure

### Phase 3: Cards & Strategy

- Full Leader card implementation
- Full Tactic card deck
- Card effects system
- Hand management UI

### Phase 4: Polish & Systems

- Visual feedback (ownership, movement, combat)
- Sound design
- Basic AI opponents (optional for single-player)
- Save/load system
- Main menu & settings

### Phase 5: Content & Balance

- Finalize all 6 factions
- Balance testing
- Additional events / objectives (stretch)
- Tutorial system

## Current Milestone Focus

**Milestone 1 – Clickable Territory Prototype**
- Goal: Prove the hybrid map system works in Godot
- Key deliverables:
  - Clickable zones with ownership
  - Basic camera movement
  - Simple visual feedback

---

**Related Notes:**
- [[Milestone 1 - Implementation Plan]]
- [[Milestone 1 - Clickable Territory Prototype]]
- [[Project Structure & Scene Organization]]
- [[Godot Workflow Notes]]
