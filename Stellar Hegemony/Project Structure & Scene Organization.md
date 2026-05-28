# Stellar Hegemony – Project Structure & Scene Organization

**Status:** Draft v2 (based on actual repo scan)  
**Last Updated:** 2026-05-28  
**Contributors:** Ron + Skippy

## Current Repository Structure

```
game/
├── assets/
│   ├── sprites/
│   │   ├── cards/
│   │   │   ├── leaders/          # [Faction]_leader.jpg
│   │   │   └── tactics/          # [Card_Name].jpg (Title_Case)
│   │   └── icons/
│   │       └── icons-dice/       # Dice_[n].png
│   ├── audio/
│   ├── fonts/
│   ├── models/
│   └── textures/
├── scenes/
│   ├── entities/
│   ├── levels/
│   └── ui/
├── scripts/
│   ├── autoloads/
│   ├── components/
│   └── ui/
├── resources/
├── addons/
└── ui/
```

## Existing Naming Conventions (Already in Use)

| Category       | Format                        | Examples                                      |
|----------------|-------------------------------|-----------------------------------------------|
| Leader Cards   | `[Faction]_leader.jpg`        | `Ants_leader.jpg`, `Birds_leader.jpg`         |
| Tactic Cards   | `[Card_Name].jpg`             | `Converge_on_the_Core.jpg`, `Hyperspace_Invasion.jpg` |
| Dice Icons     | `Dice_[number].png`           | `Dice_1.png` → `Dice_6.png`                   |

## Recommended Additions / Improvements

### Scene Organization
- Keep `scenes/levels/` for main playable maps
- Use `scenes/entities/` for reusable pieces (fleets, leaders, zones)
- Keep UI scenes in `scenes/ui/`

### Script Organization
- `scripts/autoloads/` → Singletons (GameManager, MapManager, etc.)
- `scripts/components/` → Reusable logic (ZoneLogic, FleetMovement, etc.)
- `scripts/ui/` → UI controllers

### Proposed New Conventions
- Scene files: `PascalCase.tscn` (e.g. `MainMenu.tscn`, `GalaxyMap.tscn`)
- Script files: `PascalCase.gd` matching the scene or component name
- Resources: Use `.tres` files where possible for data-driven design
