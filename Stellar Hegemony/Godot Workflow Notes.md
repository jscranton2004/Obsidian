# Godot Workflow Notes

**Last Updated:** 2026-05-28  
**Status:** Draft

## Project Setup

- **Godot Version:** 4.6.3 (stable)
- **Project Location:** `C:\Git\stellar-hegemony\game`
- **Recommended Godot Settings:**
  - Use **Forward+** renderer (best quality for stylized look)
  - **V-Sync:** Enabled (for smooth retro feel)
  - **Physics:** Jolt Physics (if available) or default

## Running the Project

```bash
# From the game/ folder
godot --path . --editor
# or simply double-click project.godot
```

For quick testing:
- Use `F5` to run the current scene
- Use `F6` to run the main scene

## Asset Import Conventions

### Images / Sprites
- All leader and tactic cards are `.jpg` with strong black borders (1950s retro style)
- Dice icons are `.png` with transparency where needed
- Import settings:
  - **Texture > Filter:** Nearest (for pixel-art / retro feel)
  - **Texture > Repeat:** Disabled (unless specifically needed)

### 3D Models
- Use `.glb` or `.gltf` format
- Keep poly count low for performance on the hybrid map

## Version Control Best Practices

- **Never commit** `.godot/` folder or `*.import` files
- Always commit:
  - `.tscn` scenes
  - `.gd` scripts
  - `.tres` resources
  - `.godot` project settings (when intentional)
- Use clear commit messages, e.g.:
  - `feat: Add ZoneMesh component`
  - `fix: Correct fleet movement on wormhole edges`
  - `docs: Update Godot Workflow Notes`

## Recommended Scene Workflow

1. Create new scenes in `scenes/levels/` or `scenes/entities/`
2. Use `PascalCase.tscn` naming
3. Keep reusable logic in `scripts/components/`
4. Use Autoloads (`scripts/autoloads/`) for managers only

## Debugging Tips

- Use `print()` liberally during early development
- Enable **Visible Collision Shapes** when working on map interaction
- Use the **Remote** tab in the editor to inspect live node values

## Export Settings (Future)

- **Platform:** Windows Desktop (primary)
- **Export Template:** Use release template for final builds
- **Icon:** Use the main game icon with 1950s styling

---

**Related Notes:**
- [[Project Structure & Scene Organization]]
- [[Stellar Hegemony - Milestone 1 - Implementation Plan]]
