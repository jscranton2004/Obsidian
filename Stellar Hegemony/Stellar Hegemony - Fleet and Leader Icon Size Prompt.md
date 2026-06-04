# Stellar Hegemony - Fleet and Leader Icon Size Prompt

**Status:** Ready to start  
**Related:** [[Stellar Hegemony - Unit Representation in Zones - Implementation Notes]], [[Stellar Hegemony - Phase 9 Task 1 - InGame Scene & HybridMap Integration]]

## Goal
Make fleet tokens and leader/flagship icons clearly visible on zones. Currently they render as tiny clusters of pixels (as seen when 3 human fleets are deployed to Starhaven). Increase the `pixel_size` values on the Sprite3D and Label3D nodes so the icons are legible at normal camera distances while keeping the existing layout and visual style.

## Scope (Narrow)
- Locate the `pixel_size` assignments for fleet sprites, flagship/leader sprites, count badges, and leader markers inside `zone.gd`.
- Increase the `pixel_size` values (suggested starting range: 3–5× the current values) so icons are comfortably visible.
- Do not change icon loading, positioning logic, tinting, billboard behaviour, stacking logic, or any other code.
- Ensure both regular fleets and flagships/leaders scale up proportionally.

## Why This Task
The current `pixel_size` values (0.0027 for fleets, 0.0038 for flagships) were set too small. With the newly spread-out map, the icons have become almost invisible. This is a pure visual sizing fix.

## Ready-to-Use Prompt for Grok Build

```
# Prompt for Grok Build: Fleet & Leader Icon Visibility (Size Fix)

**Project:** Stellar Hegemony  
**Repo location:** C:\Git\stellar-hegemony\game (or equivalent)  
**Documentation:** Obsidian vault under Stellar Hegemony/

## Goal
Increase the rendered size of fleet tokens and leader/flagship icons on zones so they are clearly visible instead of appearing as tiny pixel clusters.

## Reference
- Current implementation is in `game/scripts/map/zone.gd`
- The tiny icons are visible in the attached screenshot (human player has 3 fleets on Starhaven — they are almost invisible).

## Scope (Narrow — do ONLY this)
- In `zone.gd`, locate the four `pixel_size` assignments inside the unit visual representation section:
  - Fleet Sprite3D: currently `0.0027`
  - Count badge Label3D: currently `0.0016`
  - Flagship/leader Sprite3D: currently `0.0038`
  - Leader marker Label3D: currently `0.0011`
- Increase all four values (recommended starting point: multiply by ~4.0 so fleets become ~0.0108, flagships ~0.0152, etc.).
- Keep the relative size difference between fleets and flagships (flagships should remain slightly larger).
- Do not modify any other code: no changes to positions, offsets, tinting, billboard, stacking logic, icon paths, or _update_visuals flow.

## Critical Requirements
- Icons must become clearly visible on zones at normal camera distances after the map was spread out.
- The change must be minimal and isolated to the size values only.

## Acceptance Criteria
- After the change, deploying fleets (e.g. 3 human fleets on Starhaven) produces clearly visible icons instead of near-invisible pixel clusters.
- Flagship/leader icons remain distinguishable from regular fleets.
- No other visual or gameplay behaviour is affected.

Please implement this cleanly. After completion, briefly describe the new pixel_size values chosen, show before/after examples if possible, and confirm the icons are now legible.
```

## Next Actions
1. Feed the prompt above to Grok Build (attach the screenshot showing the tiny fleet icons).
2. Test by deploying fleets in-game and observing visibility.
3. Create completion note once verified.

*Keeping the narrow-scope discipline.*