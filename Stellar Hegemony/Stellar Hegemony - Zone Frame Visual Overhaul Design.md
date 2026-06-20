# Stellar Hegemony - Zone Frame Visual Overhaul Design

**Status:** Planning / Ready for Image Generation  
**Related GitHub Issue:** https://github.com/jscranton2004/stellar-hegemony/issues/69  
**Art Direction:** 1950s retro space / Jetson-style metallic frames with beveled edges and embellishments (consistent with other recent UI components)

## Overview
Replace the current zone presentation with a single fancy metal frame image per player count (2/3/4-player variants). This creates a cohesive board-game-on-the-table aesthetic where all zone elements live inside one generated container instead of being stacked sprites.

## Current State
- Zone image framed by a thick 3D-generated ring with control points and jagged edges.
- Primary and secondary points rendered as separate elements.
- Token placement positions exist inside the zone area.
- Ring colour changes via existing ownership/control logic (this logic **must remain unchanged**).

## New Design Requirements

### Frame Structure
- A single generated metal frame image containing:
  - Large circular cutout sized to perfectly fit the existing zone images.
  - Thinner colour-changing ring that sits **inside** the metal frame as a clean perfect circle.
  - Metal bar extending from the bottom-right of the frame.
  - Gold primary hexagon and smaller secondary hexagon positioned slightly above and to the left of the circular zone area.

### Metal Bar (Per-Player Leader + Fleet Slots)
- Exactly **1 leader slot + 1 fleet slot (with count number)** per player/bot.
- Empty-icon placeholders visible for every possible slot.
- Factions grouped contiguously (first player to place units takes the first set of slots; subsequent factions take the next).
- Leader slot remains reserved/visible even if only a fleet is present for that faction.
- Bar length stretches proportionally for 2-player, 3-player, and 4-player versions.

### Point Hexagons
- Large gold hexagon for primary points.
- Smaller hexagon for secondary points.
- Positioned slightly above and to the left of the zone image area.
- Fancy, embellished metallic style matching the frame.

### Technical Constraints
- 4-player version maximum size: **1200 × 600 px**. Shorter widths for 3p and 2p variants.
- Existing zone images must fit cleanly inside the circular area.
- Zone positions, connections, and token placement coordinates **must not change**.
- New frames are static generated images. The engine composites the dynamic zone image + ring colour + points + leader/fleet tokens on top.

## Scope
This is a **visual container change only**. Core zone mechanics, point values, fleet/leader placement rules, and ring colour behaviour remain identical.

## References
- GitHub Issue #69
- Existing zone images and current ring implementation in the Godot project
- Established 1950s retro space / Jetson-style metallic UI visual direction

## Next Steps
1. Generate the three frame images via Grok Build (see companion prompt document).
2. Integrate the new frames into the HybridMap / Zone scenes.
3. Update any zone visual logic to respect the new container while preserving all existing behaviour.