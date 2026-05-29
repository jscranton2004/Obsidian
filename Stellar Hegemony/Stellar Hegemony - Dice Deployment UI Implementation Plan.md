# Stellar Hegemony - Dice Deployment UI Implementation Plan

**Status:** ✅ Implemented (narrow scope complete) — 2026-05-29 by Grok Build + team review  
**Created:** 2026-05-29  
**Scope:** Narrow — Dice roll → visual display → player selection of 2 dice for sector targeting (sum)  
**Goal:** Implement interactive dice rolling and selection sequence in Godot 4 UI. The third die is reserved for future unit count.

## Architecture
- UI scene for deployment phase (new or extension of existing UI)
- Use existing `Dice_[1-6].png` assets from `assets/sprites/icons/icons-dice/`
- Button-driven roll
- Three dice displayed as TextureRect or Button with images
- Selection mechanic: click to toggle selection (max 2 selected). Highlight selected dice (e.g. border, scale, or move to "Selected" panel)
- Live sum display of the two selected dice
- "Confirm Selection" button (enabled only when exactly 2 selected)

## Files to Create/Modify

### New Files
- `scenes/ui/DeploymentDiceUI.tscn` — Main dice panel scene
- `scripts/ui/DeploymentDiceUI.gd` — Controller script

### Asset Notes
- Dice images already exist: `Dice_1.png` ... `Dice_6.png`
- Import settings per Godot Workflow Notes: Nearest filter, no repeat

## Implementation Tasks (Bite-sized)

### Task 1: Create the UI Scene Structure
**Objective:** Set up the basic layout with Roll button, 3 dice containers, selected area, and sum label.

**Files:**
- Create: `scenes/ui/DeploymentDiceUI.tscn`

**Steps:**
1. In Godot editor, create new Control scene.
2. Add:
   - `VBoxContainer` root
   - `Button` named "RollButton" with text "Roll"
   - `HBoxContainer` named "DiceContainer" with 3 children `TextureRect` or `Button` named `Die1`, `Die2`, `Die3`
   - `HBoxContainer` named "SelectedContainer" (for visual feedback of chosen dice)
   - `Label` named "SumLabel" with text "Select two dice..."
   - `Button` named "ConfirmButton" text "Confirm Selection" (disabled initially)

### Task 2: Implement Dice Rolling Logic
**Objective:** On Roll button press, randomly assign 1-6 to each die and update textures.

**Files:**
- Create: `scripts/ui/DeploymentDiceUI.gd`

**Code sketch (minimal):**
```gdscript
extends Control

@onready var roll_button: Button = $RollButton
@onready var dice: Array[TextureRect] = [$DiceContainer/Die1, $DiceContainer/Die2, $DiceContainer/Die3]
@onready var sum_label: Label = $SumLabel
@onready var confirm_button: Button = $ConfirmButton

var dice_values: Array[int] = [0, 0, 0]
var selected_indices: Array[int] = []

const DICE_TEXTURES = [
    preload("res://assets/sprites/icons/icons-dice/Dice_1.png"),
    # ... up to Dice_6.png
]

func _ready():
    roll_button.pressed.connect(_on_roll_pressed)
    confirm_button.pressed.connect(_on_confirm_pressed)
    # Connect die clicks
    for i in 3:
        dice[i].gui_input.connect(_on_die_input.bind(i))

func _on_roll_pressed():
    for i in 3:
        dice_values[i] = randi_range(1, 6)
        dice[i].texture = DICE_TEXTURES[dice_values[i] - 1]
    selected_indices.clear()
    _update_ui()

func _update_ui():
    # Update selection visuals and sum
    pass
```

### Task 3: Implement Selection Interaction
**Objective:** Clicking a die toggles selection (max 2). Visual highlight + optional move to selected area. Show live sum.

**Selection rules:**
- Can select up to 2 dice
- Clicking a selected die deselects it
- Sum only shown when exactly 2 are selected

**Visual ideas (choose one or combine):**
- Change modulate to yellow when selected
- Add a border via StyleBox
- Scale up slightly
- Move TextureRect to SelectedContainer when selected (simple swap)

### Task 4: Wire Up Confirm Button & Signals
**Objective:** Enable Confirm only when 2 dice selected. Emit signal with the chosen dice values (sum + leftover die) for future integration.

**Signal example:**
```gdscript
signal dice_selection_confirmed(sector_sum: int, unit_die: int)
```

### Task 5: Testing & Polish
- Test rolling multiple times
- Verify selection/deselection works intuitively
- Ensure sum updates live
- Add simple sound or animation if assets exist (optional, keep narrow)

## Verification
After implementation:
- Press Roll → 3 random dice faces appear
- Click dice → clear visual selection of exactly two
- Sum label shows e.g. "Sector target: 7 (3+4)"
- Confirm button works only with 2 selected

## Future Hooks (Not Implemented)
- Pass the sector_sum and leftover die to Map/Deployment system
- Integrate with reserves tracking
- Zone highlighting based on sum

**Next:** Once this is done and reviewed, we can move to zone targeting integration.
