# Stellar Hegemony - Zone Value Assignment - Implementation Notes

**Implemented:** 2026-05-29 by Grok Build  
**Status:** Complete (narrow scope)

## What Was Actually Built

### New Structure: `SECTOR_DATA`
- A complete array of all 11 sectors now lives in `hybrid_map.gd`
- Each entry contains:
  - `name` (thematic name from Sector Map Reference)
  - `id` (stable identifier, currently using the original 2–12 numbers)

This replaced the old 7-zone `M1_ZONE_DATA`.

### Core Method: `_setup_zones_for_new_game()`
- Called from `HybridMap._ready()`
- Builds the set `[2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]`
- Shuffles it using Godot’s `Array.shuffle()` (Fisher-Yates)
- Assigns each value exactly once to a zone’s `zone_value`
- Includes console output + uniqueness sanity check on every new game

### Scene Changes
- `HybridMap.tscn` no longer has the 7 old static Zone children
- Zones are now created dynamically in code so random assignment can occur at game start

### Current Location of Logic
- The assignment logic currently lives in `HybridMap._ready()` (prototype convenience)
- A public `start_new_game()` method was suggested as a future hook for a proper GameManager

## Testing (as verified by Grok)

1. Run `scenes/levels/Main.tscn`
2. Watch the Output console — you should immediately see:
   - "HybridMap: New game started – 11 zones created with unique 2–12 point values."
   - The full list of 11 sectors with their randomly assigned values
   - A uniqueness confirmation
3. Re-run the scene multiple times → different assignments each time
4. Dice deployment UI continues to work unchanged via `get_zone_by_value()`

## Future Considerations (not implemented)

- Expose a public `start_new_game()` method
- Move logic out of `_ready()` into a proper game flow
- Add persistence / save support later
- Reorder `SECTOR_DATA` to match the exact sequence in the Sector Map Reference if desired

---

*This note captures the actual delivered implementation for future reference.*