# Stellar Hegemony - Fleet and Leader Icon Size - 10x Follow-up

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Fleet and Leader Icon Size Prompt]]

## Goal
The previous size increase was not sufficient. Scale the fleet and leader icons by a full 10× from the original values so they are comfortably visible on the spread-out map.

## Scope (Narrow)
- Update only the four `pixel_size` values in `zone.gd` to 10× their *original* sizes:
  - Fleet Sprite3D: `0.0027` → `0.027`
  - Count badge Label3D: `0.0016` → `0.016`
  - Flagship/leader Sprite3D: `0.0038` → `0.038`
  - Leader marker Label3D: `0.0011` → `0.011`
- Leave all other code, positions, logic, and styling exactly as it is.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Fleet & Leader Icon Size — 10× Increase

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)

## Goal
The previous size adjustment was still too small. Make fleet and leader icons 10× larger than the original values so they are clearly visible on the map.

## Scope (Narrow — do ONLY this)
In `game/scripts/map/zone.gd`, change only these four `pixel_size` lines to 10× their original values:

- Fleet Sprite3D: change `0.0027` to `0.027`
- Count badge Label3D: change `0.0016` to `0.016`
- Flagship/leader Sprite3D: change `0.0038` to `0.038`
- Leader marker Label3D: change `0.0011` to `0.011`

Do not touch anything else — no position changes, no logic changes, no other files.

## Acceptance Criteria
- Fleet and flagship icons are now large enough to be easily seen on zones at normal camera distances.
- The relative size difference between fleets and flagships is preserved.
- Everything else (stacking, tinting, positioning, billboard, etc.) remains unchanged.

Please apply the four value changes and confirm the new sizes.
```

## Next Actions
1. Send the prompt above to Grok Build.
2. Test visibility in-game.
3. Create completion note when done.

*Keeping the narrow-scope discipline.*