# Stellar Hegemony - Fleet and Leader Icon Positioning Fix

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Fleet and Leader Icon Size - 10x Follow-up]]

## Goal
After increasing `pixel_size` to 10×, the fleet and leader icons became invisible because their world-space position offsets are now too small relative to the new icon sizes. Scale the position offsets so the large icons sit visibly above the zones.

## Scope (Narrow)
- In `zone.gd`, scale the four `position` assignments for the unit sprites and badges by approximately 10×.
- Do not change `pixel_size`, icon loading, tinting, billboard, or any other logic.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Fleet & Leader Icon Positioning Fix

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)

## Goal
The 10× `pixel_size` icons are now invisible because their position offsets are too small. Scale the position values so the large icons float visibly above the zones.

## Scope (Narrow — do ONLY this)
In `game/scripts/map/zone.gd`, update only these four position lines (multiply the original offsets by ~10):

- Fleet Sprite3D: change `sprite.position = Vector3(0.32, 0, 0)` to `Vector3(3.2, 0, 0)`
- Count badge Label3D: change `badge.position = Vector3(0.78, 0.02, 0)` to `Vector3(7.8, 0.2, 0)`
- Flagship/leader Sprite3D: change `sprite.position = Vector3(-0.58, 0.07, 0)` to `Vector3(-5.8, 0.7, 0)`
- Leader marker Label3D: change `marker.position = sprite.position + Vector3(0, 0.22, 0)` to `marker.position = sprite.position + Vector3(0, 2.2, 0)`

Keep the relative layout (fleet on the right, flagship on the left, badge further right, marker above flagship).

## Acceptance Criteria
- Fleet and leader icons are now clearly visible and properly offset above the zone surface.
- The icons remain billboarded and correctly tinted.
- No other code or behaviour is changed.

Please apply only these four position changes and verify the icons appear correctly on The Core (or any zone with fleets).
```

## Next Actions
1. Send the prompt to Grok Build.
2. Test by deploying fleets and observing The Core / Starhaven.
3. Create completion note when icons are visible and correctly positioned.

*Keeping the narrow-scope discipline.*