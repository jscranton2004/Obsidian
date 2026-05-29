# Stellar Hegemony - Unit Representation Planning

**Status:** Planning / Definition  
**Date:** 2026-05-29  
**Purpose:** Clearly define how Fleets and Leaders appear when placed in zones before implementing deployment logic.

## Core Rule
Both the **Leader (Flag Ship)** and **Fleet tokens** count as **units** for the purposes of sector control and final scoring.

## Visual Assets (Confirmed)

### Fleet Tokens
- **Location:** `assets/sprites/icons/icons-fleets/`
- One unique fleet icon exists per race (Ants, Humans, Rocks, Birds, Blobs, Fishs)
- These are the standard tokens used to represent a player’s military presence in a zone.

### Leader / Flag Ship Tokens
- **Location:** `assets/sprites/icons/icons-leaders/`
- One dedicated leader board icon exists per race
- These represent the player’s chosen Flag Ship when placed on the map
- Distinct from the larger leader card art (`cards/leaders/`)

## Representation When Placed in a Zone

### Fleet Representation
- When a fleet is placed in a zone, it should use the appropriate race’s fleet icon from `icons-fleets/`
- Multiple fleets of the same player in one zone can be stacked or shown with a count (to be decided during UI implementation)

### Leader / Flag Ship Representation
- When a player’s chosen leader is placed in a zone, it should use the corresponding icon from `icons-leaders/`
- The Flag Ship should be visually distinct from regular fleet tokens (different size, border treatment, or highlight)
- Only one Flag Ship per player can exist on the map at a time

## Important Notes for Future Implementation

- Both Fleets and the Flag Ship contribute to a player’s total unit count in a zone for control purposes.
- Ownership colour tinting should apply to both fleet and leader icons.
- Hover/selection feedback should work on both types of tokens.
- The Flag Ship may have special visual treatment when it is the only unit in a zone.

## Next Steps (Recommended Order)

1. Finalise this representation definition (current step)
2. Implement basic zone unit display (showing fleets + leader icons)
3. Add deployment logic that places fleets and the leader into zones
4. Connect leader selection to the player’s starting Flag Ship

---

*This note exists to reduce ambiguity before coding begins.*