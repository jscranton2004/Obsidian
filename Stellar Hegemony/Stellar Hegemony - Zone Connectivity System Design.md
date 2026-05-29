# Stellar Hegemony - Zone Connectivity System Design

**Status:** Design / Planning  
**Date:** 2026-05-29  
**Purpose:** Define the Zone Connectivity System required for Tactic/Leader card effects and future movement rules.

## Overview
The game uses a hybrid map with 11 zones. Movement and many card effects depend on knowing which zones are connected and the **type** of connection (hyperspace vs wormhole).

## Requirements

### Connection Types
The system must support three categories of connections:

1. **Standard Adjacency** — Zones connected by either hyperspace or wormhole.
2. **Hyperspace-only** — Normal movement routes.
3. **Wormhole-only** — Special/faster movement routes (can be one-way in the future).

### Core Queries Needed
The system should provide the following queries:

- `get_adjacent_zones(zone)` — Returns all zones connected by any route.
- `get_hyperspace_connected_zones(zone)` — Returns only hyperspace connections.
- `get_wormhole_connected_zones(zone)` — Returns only wormhole connections.
- `get_connection_type(zone_a, zone_b)` — Returns the type(s) of connection between two zones.

### Data Model Recommendations

**Option A (Recommended for flexibility)**
Store connections as a dictionary or resource on `HybridMap`:

```gdscript
var zone_connections: Dictionary = {
    2: { "hyperspace": [5, 6, 12], "wormhole": [] },
    5: { "hyperspace": [2, 3, 6], "wormhole": [4] },
    ...
}
```

**Option B**
Create a `ZoneConnection` resource or small class that can be attached to zones or stored centrally.

### Integration Points
- `HybridMap` should expose the connectivity queries.
- `Zone` nodes may need a reference back to the map or a zone ID.
- Tactic/Leader card effects will rely heavily on these queries.
- Future fleet movement rules will also use this system.

## Scope for Initial Implementation
- Hardcode or configure the 11-zone connection graph based on the **Sector Map Reference**.
- Support bidirectional connections for now (one-way wormholes can be added later).
- Provide clean query methods as listed above.

## References
- `Stellar Hegemony - Sector Map Reference.md` — Contains the full connection data for all 11 sectors.
- `Stellar Hegemony - Tactic and Leader Card Effects Design.md`
- `Stellar Hegemony - Core Mechanics.md`

---

*This system is a foundational prerequisite for card effects and movement.*