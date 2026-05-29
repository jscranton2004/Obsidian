# Stellar Hegemony - Unit Representation in Zones - Implementation Notes

**Implemented:** 2026-05-29 by Grok Build  
**Status:** Complete (narrow scope)

## What Was Delivered

### Main Changes
- Enhanced `game/scripts/map/zone.gd`
  - Added `fleet_count` and `has_flagship` exports
  - Added `_update_unit_visuals()` method that dynamically creates `Sprite3D` tokens
  - Fleet icons pulled from `icons-fleets/`
  - Flag Ship icons pulled from `icons-leaders/`
  - Ownership tinting via `modulate`
  - Simple "xN" count badge for stacked fleets
  - Flag Ship rendered larger with a "♦" marker for distinction
  - Full backward compatibility with previous `unit_count` system

### Demo / Test Data
- `game/scripts/map/hybrid_map.gd` — Demo zones now show realistic fleet + flagship combinations
- `game/scenes/Map/Zone.tscn` — Added the two new exports to the base scene

### Visual Approach
- Units are created as `Sprite3D` nodes inside a `UnitTokens` container
- Billboarding enabled so tokens face the camera
- Clean, retro-friendly "xN" stacking badge
- Flag Ship clearly differentiated by size + marker

## Scope Discipline
- No new token scenes created
- No deployment or movement logic
- No combat or control resolution
- No UI interaction
- Kept strictly to visual representation only

## Testing Instructions (from Grok)

1. Open `scenes/levels/Main.tscn`
2. Run the scene (F5)
3. Inspect "The Core" zone (Human demo):
   - Should show a tinted Human fleet icon + "x2" badge
   - Next to it: a larger Flag Ship icon with "♦" marker
4. Rotate the camera — tokens are billboarded
5. In the editor, select a Zone → Inspector → live-edit `fleet_count` / `has_flagship` / `owner_faction`

## Assumptions Made
- Single owner per zone for now (multi-faction support can be added later)
- Dynamic `Sprite3D` creation (no extra `.tscn` boilerplate)
- Simple "xN" badge for stacking (matches planning guidance)
- Flag Ship distinction via size + offset + "♦" marker

---

*Clean, focused implementation that satisfies all acceptance criteria while staying narrow.*