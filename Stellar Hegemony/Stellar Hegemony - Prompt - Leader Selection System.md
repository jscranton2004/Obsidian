# Prompt for Grok Build: Leader Selection System

**Project:** Stellar Hegemony  
**Repo location:** `C:\Git\stellar-hegemony\game`  
**Documentation:** `C:\Obsidian Vault\Stellar-Hegemony\Stellar Hegemony\`

## Goal
Implement the Leader selection system that runs at the start of every game.

## Key Rules (from Core Mechanics + team requirements)

There are exactly **6 possible leaders** with the following full names and titles:

- **Commander Skitter** (Ant-men) – *The Swarm Lord*
- **Admiral Vance "Ironjaw" Hale** (Human) – *The Last Terran*
- **High Lord Glubthar** (Fish-men) – *Voice of the Abyssal Current*
- **Sky Marshal Quill** (Bird-men) – *The Stormfeather*
- **Lord Granite** (Rock-men) – *The Unmoving*
- **The Many** (Weird Blobs) – *The Thousand-Minded*

### Selection Rules
- At the start of a game, the number of leaders presented = **number of players + 1**
- Maximum 4 players → therefore **one leader is always randomly excluded**
- The player who goes **last** picks their leader **first**
- Once a leader is chosen, it is removed from the pool
- Each player may only select **one** leader

- Turn order must also be determined at the start of each game (random or defined order)

## Current State
- Leader card images exist in `game/assets/sprites/cards/leaders/`
- No leader selection system has been implemented yet
- No player/turn order system exists yet

## What Needs to Be Built (narrow scope)

Create a **Leader Selection System** that handles:

1. Determining the number of players (for now, accept a parameter or use a simple default)
2. Randomly selecting `(players + 1)` leaders out of the 6
3. Establishing a random turn order for the players
4. Allowing players to pick leaders in **reverse turn order** (last player picks first)
5. Removing chosen leaders from availability

## Strict Requirements

- Use the exact 6 leaders with their full names and titles listed above.
- The system must be easily callable at game start (suggest a `start_new_game(players: int)` style method).
- Keep scope narrow — do **not** implement the actual leader card effects, UI for picking, or player data models yet.
- Focus on the **logic** of:
  - Random leader pool generation
  - Turn order determination
  - Reverse-order picking sequence

## Acceptance Criteria

- With 2 players → exactly 3 leaders are offered
- With 3 players → exactly 4 leaders are offered
- With 4 players → exactly 5 leaders are offered (1 always excluded)
- The last player in turn order always picks first
- No leader can be chosen by more than one player
- Running multiple games produces different random leader pools and turn orders

## Files You Will Likely Touch
- `game/scripts/map/hybrid_map.gd` or a new `game/scripts/systems/leader_manager.gd`
- Possibly create a small autoload or GameManager if it makes sense

## Documentation References
- Core Mechanics: `Stellar Hegemony - Core Mechanics.md`
- Full leader names & titles: `Stellar Hegemony - Adapted Flag Ship Cards.md`
- Asset folder: `game/assets/sprites/cards/leaders/`

Please implement this cleanly with good comments. After completion, briefly describe:
- What was created
- How to test the logic
- Any assumptions made

This is a narrow-scope task focused only on the selection logic and turn order.