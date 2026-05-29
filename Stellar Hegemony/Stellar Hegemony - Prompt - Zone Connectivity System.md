# Prompt for Grok Build: Zone Connectivity System

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Zone Connectivity System that allows the game to query which zones are connected and the **type** of connection.

## Key Reference Documents
- `Stellar Hegemony - Zone Connectivity System Design.md` (primary reference)
- `Stellar Hegemony - Sector Map Reference.md` (contains the complete 11-sector connection data)
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md`

## Requirements

### Connection Types
The system must correctly distinguish between three categories:

- **Standard Adjacency** — A zone is adjacent if it is connected by **either** hyperspace **or** wormhole.
- **Hyperspace-only** — Connections that can only be used via hyperspace lanes.
- **Wormhole-only** — Connections that can only be used via wormholes.

### Required Query Methods
Implement the following methods on `HybridMap`:

| Method                                | Purpose                                                                 | Wormholes allowed? | Hyperspace allowed? |
|---------------------------------------|-------------------------------------------------------------------------|--------------------|---------------------|
| `get_adjacent_zones(zone_id)`         | Returns all zones connected by any route                                | Yes                | Yes                 |
| `get_hyperspace_connected_zones(zone_id)` | Returns only zones connected via hyperspace                         | No                 | Yes                 |
| `get_wormhole_connected_zones(zone_id)`   | Returns only zones connected via wormhole                           | Yes                | No                  |
| `get_connection_type(zone_a, zone_b)`     | Returns the type(s) of connection between two zones                 | —                  | —                   |

### Data Source
Use the connection data from **`Stellar Hegemony - Sector Map Reference.md`** to build the initial 11-zone graph.

### Scope (Narrow)
- Focus on providing reliable, correctly typed query methods.
- Connections can be hardcoded or stored in a simple dictionary for now.
- Do **not** implement:
  - One-way wormholes
  - Visual connection lines
  - Pathfinding
  - Integration with card effects

## Acceptance Criteria

- `get_adjacent_zones(5)` returns all neighbors of The Core (both hyperspace and wormhole).
- `get_hyperspace_connected_zones(4)` returns only hyperspace connections.
- `get_wormhole_connected_zones(4)` returns only wormhole connections.
- `get_connection_type(2, 12)` correctly reports the connection type.
- The system works with the existing zone numbering (2–12).

## Files You Will Likely Touch
- `game/scripts/map/hybrid_map.gd`

## Important Notes
- The distinction between “adjacent” (either route) and the specific route types is critical for Tactic and Leader card effects.
- Refer to the **Zone Connectivity System Design** note for the full intended semantics.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How to test the connectivity queries
- Any assumptions made

This is a narrow-scope task.