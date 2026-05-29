# Prompt for Grok Build: Unit Representation in Zones

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the visual representation of units (Fleets and Flag Ships) when placed inside zones.

## Key Reference Documents
- `Stellar Hegemony - Unit Representation Planning.md` (primary reference)
- `Stellar Hegemony - Asset Structure.md`
- `Stellar Hegemony - Core Mechanics.md`

## Requirements

### Assets to Use
- **Fleet tokens**: Use the icons from `assets/sprites/icons/icons-fleets/`
- **Leader / Flag Ship tokens**: Use the icons from `assets/sprites/icons/icons-leaders/`
- One unique icon exists per race for both fleets and leaders.

### Visual Behaviour in Zones
- When a player has fleets in a zone, display the appropriate fleet icon (with ownership colour tint).
- When a player’s Flag Ship is in a zone, display the corresponding leader icon from `icons-leaders/`.
- The Flag Ship icon should be visually distinct from regular fleet icons.
- Both fleets and the Flag Ship count as **units** for zone control and scoring.

### Scope (Narrow)
- Focus only on **displaying** units inside zones.
- Support basic stacking / count display for multiple fleets of the same player.
- Apply ownership colour tinting.
- Do **not** implement:
  - Actual deployment / movement logic
  - Clicking or selecting units
  - Combat or control resolution
  - Leader effects

## Acceptance Criteria

- A zone can display both fleet icons and a Flag Ship icon belonging to the same player.
- Fleet and Flag Ship icons use the correct race-specific assets from the `icons-fleets/` and `icons-leaders/` folders.
- Ownership colour is clearly visible on both types of tokens.
- Multiple fleets of the same player are visually grouped or counted.
- The Flag Ship is distinguishable from regular fleets.

## Files You Will Likely Touch
- `game/scripts/map/zone.gd` (or a new component for unit display)
- Possibly `game/scenes/entities/` for reusable unit token scenes

## Important Notes
- Refer to the **Unit Representation Planning** note for the intended visual treatment.
- Keep the implementation minimal and focused on representation only.

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How to test the visual representation
- Any assumptions made

This is a narrow-scope task focused only on how units appear inside zones.