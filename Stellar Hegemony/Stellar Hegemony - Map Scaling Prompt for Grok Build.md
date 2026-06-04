# Stellar Hegemony - Map Scaling Prompt for Grok Build

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - HybridMap Base Layer - Implementation Notes]], [[Stellar Hegemony - Sector Map Reference]], [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

## Goal
Adjust the existing zone positions on the HybridMap so they are spread out significantly farther from the center while preserving the exact overall shape, relative layout, connections, and topology. The map should feel much larger (matching the spread of `Wide_map.jpg`) so the player will need to pan and zoom the camera rather than seeing everything compressed on screen.

## Scope (Narrow)
- Identify the current zone positions (the clustered layout defined in `game/scripts/map/hybrid_map.gd`).
- Choose a clear center point (The Core or the geometric centroid of all zones).
- Scale every zone's position by multiplying its offset vector from the center by a uniform expansion factor (choose an appropriate factor ~2.2–2.8 so the layout matches the spread of `game/assets/reference/Wide_map.jpg` while still fitting comfortably on the large 5120×1440 nebula plane).
- Update only the position values — do not change any connections, zone names, materials, or logic.
- Ensure the overall shape and relative angles/distances ratios remain identical (no reshuffling or randomization).

## Why This Task
The current implementation has correct positions, shape, and connections but is too compressed. `Wide_map.jpg` shows the desired spread. We want the player to explore the map via camera controls rather than having everything squished into the viewport.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Map Scaling / Spread Adjustment

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Scale up the zone layout on the HybridMap by pushing all zones farther away from a central point. The result must look like the spread-out reference image while keeping the exact same overall shape and connections as the current clustered implementation.

## Reference Image (local file — read directly from disk)
- `game/assets/reference/Wide_map.jpg` — the canonical spread-out reference layout. Use this as the visual target for final spacing and proportions.
- The current clustered positions are defined in `game/scripts/map/hybrid_map.gd` (the `SECTOR_DATA` array, lines 58-71).

## Scope (Narrow — do ONLY this)
- Locate the 11 zone positions in `game/scripts/map/hybrid_map.gd` (SECTOR_DATA).
- Determine the center point: either the position of "The Core" (id 5) or the average/centroid of all current zone positions.
- For each zone, calculate its offset vector from the center, multiply that vector by a uniform scale factor (choose ~2.2–2.8 so the final layout matches the visual spread of `Wide_map.jpg` while staying well within the 5120×1440 nebula plane).
- Apply the new scaled positions back into the SECTOR_DATA array (or wherever they are instantiated).
- Leave every connection, adjacency list, wormhole/hyperspace type, zone name, and all other data completely unchanged.
- Do not alter camera, materials, shaders, or any gameplay logic.

## Critical Requirements (non-negotiable)
- The overall shape, relative positions between zones, and connection topology MUST remain exactly the same — only distances from the center are increased.
- No randomization, no reordering, no creative reinterpretation of the layout.
- The new layout must feel "larger" and require panning/zooming, exactly as described.

## Acceptance Criteria
- After the change, the zones visually match the spread of `Wide_map.jpg` while preserving the precise shape of the current implementation.
- All existing connections and gameplay behavior remain identical.
- The map still fits on the large nebula plane and looks balanced.

Please implement this cleanly. After completion, briefly describe the center point chosen, the exact scale factor used, the before/after position changes (list a few examples), how to test, and any assumptions.
```

## Next Actions
1. Feed the prompt above to Grok Build (it can read `Wide_map.jpg` directly from the repo — no attachments needed).
2. Review the delivered changes for mechanical fidelity.
3. Create completion note once verified and tested.
4. Commit the updated vault note.

*Keeping the narrow-scope discipline and exact mechanical fidelity.*