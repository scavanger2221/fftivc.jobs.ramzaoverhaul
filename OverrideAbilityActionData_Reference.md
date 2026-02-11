# OverrideAbilityActionData Table Reference

## Column Meanings

| Column | Description | Notes |
|--------|-------------|-------|
| **Key** | Ability ID | Matches Ability-en table ID |
| **unused** | Unused | Always -1 |
| **Flags12** | Ability Flags 1 & 2 | Array of 2 shorts |
| **Flags34** | Ability Flags 3 & 4 | Array of 2 shorts |
| **Range** | Horizontal Range | How far the spell reaches |
| **EffectArea** | Area of Effect (AoE) | 0 = single target, 1 = 1 tile, 2 = 2 tiles, etc. |
| **Vertical** | Vertical Tolerance | Height difference allowed |
| **Element** | Elemental Attribute | Fire/Ice/etc. |
| **Formula** | Damage Formula ID | Determines how damage is calculated |
| **X** | Damage Modifier | Increases spell power/damage |
| **Y** | Accuracy/Status Hit Rate | For status spells, increases success rate |
| **InflictStatus** | Status Effect ID | Which status to apply |
| **CT** | Charge Time (Cast Time) | Turns to charge before casting |
| **MPCost** | MP Cost | Mana required to cast |

## Value Conventions

- **-1** = Use vanilla game value (no override)
- **0 or greater** = Override the vanilla value

## Common Patterns

### Damage Spells
- **X** values increase damage (e.g., Firaja X=36 = +20% damage)
- **Formula** determines damage calculation type

### Status Spells
- **Y** values increase accuracy (e.g., Mystic skills Y=220 = +20 accuracy)

### AoE Spells
- **EffectArea** = radius around target
- **Range** = distance from caster to target center

## Current Mod Changes

### Tier 1 Spells (Protect/Shell)
- CT 3 (faster casting)

### -ja Spells (Curaja, Protectja, Shellja, Hasteja, Slowja)
- Range 4, EffectArea 2 (nerfed from vanilla)

### Ultimate Spells
- Meteor: 40 MP, CT 8
- Flare: X 48 (damage buff)
- Ultima: 15 MP, CT 4, Formula 32, X 34, Y 32

### Summons
- Various CT adjustments (3-10)
- Lich: 50 MP

### Mystic/Oracle
- All status spells: +20 accuracy (Y values 140-220)

### Squire Skills
- Rush: 0 MP, 0 CT
- Throw Stone: 0 MP, 0 CT

### Sap Skills
- All: 0 MP, 0 CT

### Cloud Limit Breaks
- Various CT adjustments (2-10)
