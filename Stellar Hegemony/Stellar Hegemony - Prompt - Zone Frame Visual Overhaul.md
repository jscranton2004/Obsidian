# Stellar Hegemony - Prompt - Zone Frame Visual Overhaul

**Reference Documents:**
- [[Stellar Hegemony - Zone Frame Visual Overhaul Design]]
- GitHub Issue: https://github.com/jscranton2004/stellar-hegemony/issues/69

**Strict Narrow Scope:** Generate the three metal frame images only. Do not modify any Godot code, scenes, or scripts.

## Task
Generate three high-quality metallic frame images (one for each player count) for the new zone UI in Stellar Hegemony.

### Required Output
Create exactly three images:
1. **2-player version**
2. **3-player version**
3. **4-player version**

### Image Specifications
- **4-player version maximum dimensions:** 1200 × 600 px. Make the 3-player and 2-player versions proportionally shorter in width while maintaining visual consistency.
- Style: **1950s retro space / Jetson-style** — fancy, embellished metal frames with beveled edges, metallic textures, brushed steel/brass/gold accents, and decorative detailing consistent with other UI components in the project.

### Frame Elements (all contained on a single image)
- Large circular cutout sized so existing zone images fit perfectly inside.
- Thin metal ring (as a perfect circle) framing the circular cutout area (this will sit inside the main frame).
- Metal bar extending from the bottom-right of the frame.
- Large gold hexagon (primary points) and smaller hexagon (secondary points) positioned slightly above and to the left of the circular zone area.
- The metal bar must clearly show slots for **1 leader + 1 fleet (with count)** per player, with visible empty placeholders.
- Faction grouping should feel natural (slots are contiguous per faction).

### Important Constraints
- Do **not** change zone positions, connections, or token placement logic.
- The ring colour change logic remains untouched in code — the frame simply provides a thinner, cleaner circular border.
- Existing zone images must fit cleanly in the circular area.
- All embellishments and styling must match the established retro space metallic look.

## Acceptance Criteria
- Three images delivered matching the player counts above.
- Clean circular cutout for zone images.
- Clear per-player leader + fleet slots with empty placeholders.
- Gold hexagons positioned above-left of the zone area.
- Consistent 1950s retro space / Jetson metallic style with bevels and embellishments.
- Correct sizing (≤1200×600 for 4p).

## After Completion
Briefly describe what was generated and any assumptions made. Provide the file paths or asset names for the three images.