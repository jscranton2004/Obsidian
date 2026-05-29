# Prompt for Grok Build: Zone Connectivity System

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Zone Connectivity System that allows querying which zones are connected and the type of connection (hyperspace vs wormhole).

## Key Reference Documents
- `Stellar Hegemony - Zone Connectivity System Design.md` (primary reference)
- `Stellar Hegemony - Sector Map Reference.md` (contains the full 11-sector connection data)
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md`

## Requirements

### Connection Types
The system must support three categories:
- **Standard Adjacency** — Any connection (hyperspace or wormhole)
- **Hyperspace-only** connections
- **Wormhole-only** connections

### Required Queries
Implement the following methods on `HybridMap` (or a dedicated manager):

- `get_adjacent_zones(zone_id)` → Returns all connected zones
- `get_hyperspace_connected_zones(zone_id)` → Hyperspace only
- `get_wormhole_connected_zones(zone_id)` → Wormhole only
- `get_connection_type(zone_a, zone_b)` → Returns the connection type(s) between two zones

### Data Source
Use the connection data from the **Sector Map Reference** document to build the initial graph for all 11 zones.

### Scope (Narrow)
- Focus on providing reliable query methods.
- Connections can be hardcoded or loaded from a simple data structure for now.
- Do **not** implement:
  - One-way wormholes
  - Visual representation of connections
  - Pathfinding
  - Integration with card effects yet

## Acceptance Criteria

- `get_adjacent_zones(5)` returns the correct neighbors of The Core.
- `get_wormhole_connected_zones(4)` returns only zones connected by wormhole.
- `get_connection_type(2, 12)` correctly identifies the connection type.
- The system works with the existing zone ID system (2–12).

## Files You Will Likely Touch
- `game/scripts/map/hybrid_map.gd`

## Important Notes
- Refer to the **Zone Connectivity System Design** note for the intended approach.
- This system is a prerequisite for most Tactic and Leader card effects.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How to test the connectivity queries
- Any assumptions made

This is a narrow-scope task.