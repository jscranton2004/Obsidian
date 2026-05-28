# Stellar Hegemony - Asset Structure

**Status:** Initial Setup

## Current Committed Assets (as of 27 May 2026 push)

**Total files added in batch:** 36

**Contents:**
- **Leader Cards** (`cards/leaders/`): All 6 races (Ants, Humans, Rocks, Birds, Blobs, Fishs)
- **Tactic Cards** (`cards/tactics/`): Full set of tactic cards
- **Dice Icons** (`icons/`): Dice faces 1–6
- **Fleet Icons** (`icons/icons-fleets/`): One unique fleet icon per race
- **Leader Board Icons** (`icons/icons-leaders/`): One leader icon per race

All assets follow the 1950s retro space / Atompunk / Jetson aesthetic with strong black borders.

## Leader Cards (Static Prototypes)

**Location on local machine:**
`C:\Git\stellar-hegemony\game\assets\sprites\cards\leaders`

**Current files:**
- `Ants_leader.jpg`
- `Humans_leader.jpg`
- `Rocks_leader.jpg`
- `Birds_leader.jpg`
- `Blobs_leader.jpg`
- `Fishs_leader.jpg`

These are 1950s retro space / Jetson-style leader portraits generated for rapid prototyping and inspiration. They will later be replaced with animated versions.

## Full Folder Structure (as of 27 May 2026)

```
assets/
├── sprites/
│   ├── cards/
│   │   ├── leaders/      ← Leader card art (Ants, Humans, Rocks, Birds, Blobs, Fishs)
│   │   └── tactics/      ← Tactic card art
│   ├── galaxy-map/       ← Sector / galaxy map assets
│   └── icons/
│       ├── icons-fleets/ ← Fleet icons (one unique per race)
│       └── icons-leaders/← Leader board icons (for placing leaders on the map)
```

**Local paths:**
- `C:\Git\stellar-hegemony\game\assets\sprites\cards\leaders`
- `C:\Git\stellar-hegemony\game\assets\sprites\cards\tactics`
- `C:\Git\stellar-hegemony\game\assets\sprites\galaxy-map`
- `C:\Git\stellar-hegemony\game\assets\sprites\icons\icons-fleets`
- `C:\Git\stellar-hegemony\game\assets\sprites\icons\icons-leaders`

## Image Generation Workflow (Grok)

**Problem:** Grok frequently fails to generate images with true transparency, even when explicitly requested.

**Recommended workaround:**

1. Generate the image with a **solid bright lime green background** (`#00FF00`).
2. Remove the green background locally using one of these tools:
   - **remove.bg** (fastest, web-based)
   - **Photopea** (free browser-based Photoshop)
   - **GIMP** (free desktop app)

3. Export as **PNG** with transparency enabled.

This method currently produces the cleanest results for Godot sprites.

**Example prompt addition:**
Add this line at the end of your prompt:
> "Solid bright lime green background (#00FF00), no shadows or gradients on the background."

---

## Godot Import Paths
- Leaders: `res://assets/sprites/cards/leaders/`
- Tactics: `res://assets/sprites/cards/tactics/`
- Galaxy map: `res://assets/sprites/galaxy-map/`
- Fleet icons: `res://assets/sprites/icons/icons-fleets/`
- Leader icons: `res://assets/sprites/icons/icons-leaders/`

---

*Note: This structure follows the Godot 4 project bootstrap recommendations.*