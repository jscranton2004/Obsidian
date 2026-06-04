# Stellar Hegemony - Fleet Icon Rendering and Positioning Fix

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Fleet and Leader Icon Positioning Fix]], [[Stellar Hegemony - Fleet and Leader Icon Size - 10x Follow-up]]

## Goal
Fix two issues visible after the 10× size + positioning changes:
1. The actual fleet icon (human-fleet.png) is not rendering — only the "×3" badge appears.
2. The visible "×3" badge is positioned far to the left of The Core instead of near or on the zone.

The unit visuals must appear directly on/above their correct zone.

## Scope (Narrow)
- Investigate why the fleet Sprite3D is not being added in `_update_unit_visuals()`.
- Adjust the position offsets for both the fleet sprite and badge so they sit visibly on top of the zone (relative to the zone's local origin).
- Do not change `pixel_size`, icon loading logic, or any other behaviour.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Fleet Icon Rendering + Positioning Fix

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)

## Goal
Two problems exist after the previous size/position changes:
1. The fleet icon itself is not rendering (only the "×3" badge is visible).
2. The visible badge is positioned far away from its zone ("The Core") instead of on or near it.

## Reference
- Screenshot shows human player deployed 3 fleets to The Core (log confirms this), but the fleet icon is missing and the badge is way off to the left.

## Scope (Narrow — do ONLY this)
In `game/scripts/map/zone.gd`:

1. Check `_update_unit_visuals()` and ensure the fleet Sprite3D is actually being created and added when `fcount > 0`.
2. Adjust the four position values so the unit visuals appear directly on/above the zone (they are currently too far away):
   - Fleet sprite position
   - Badge position
   - Flagship sprite position
   - Marker position

Suggested approach: reduce the large offsets (3.2, 7.8, etc.) to much smaller values that keep the icons visually attached to the zone (e.g. 0.8–1.5 range or test values that place them clearly on the zone mesh).

Keep the relative layout (fleet to the right of center, badge further right, flagship to the left).

## Acceptance Criteria
- When 3 fleets are deployed to The Core, both the fleet icon and the "×3" badge appear visibly on or directly above The Core.
- The fleet sprite itself renders (not just the badge).
- Icons remain large and billboarded.
- No other code or files are changed.

Please diagnose why the fleet sprite isn't appearing and correct the position offsets so the unit visuals sit on their correct zone.
```

## Next Actions
1. Send the prompt above to Grok Build (attach the latest screenshot).
2. Test by deploying fleets to The Core and verifying both the icon and badge appear in the correct location.
3. Create completion note once fixed.

*Keeping the narrow-scope discipline.*