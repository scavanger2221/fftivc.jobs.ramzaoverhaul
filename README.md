# Ramza Progressive Overhaul & Balance Mod
### For Final Fantasy Tactics: The Ivalice Chronicles (FFTIVC)

This mod is a comprehensive rebalance of Ramza Beoulve and various job classes, equipment, and shops to provide a more progressive and rewarding experience throughout the game.

## 🚀 Key Features

### 🛡️ Ramza Progressive Evolution
Ramza now grows in power as the story progresses. His stats, innates, and equipment access evolve across Chapters 1, 2-3, and 4.
- **Chapter 1**: 115% PA, Innate Concentration.
- **Chapter 2-3**: 120% PA, Innate Concentration + Attack Boost, Heavy Armor access.
- **Chapter 4**: 125% PA, All weapon access, All hero innates, 160% HP.

### ⚔️ Equipment Overhaul
- **Genji Set**: Now truly legendary.
  - **Gloves**: +2 PA/MA, Immune Disable.
  - **Shield**: Auto-Shell, High Evasion.
  - **Armor**: +1 PA/MA, Auto-Regen.
  - **Helm**: +1 Speed, Immune Stone.
- **Heavy Armor & Helms**: Strategic trade-offs between raw HP and offensive bonuses (PA/MA).
- **Weapon Scaling**: Buffed Swords, Katanas, Spears, Daggers, Shuriken, and Guns (+1).
- **Bags & Poles**: Improved viability for Chemist and Monk builds.

### 🎭 Job Rebalances
- **Archer**: Innate Concentration, improved PA scaling.
- **Samurai**: Innate Doublehand, PAMultiplier 135 (+3).
- **Thief**: Innate Concentration.
- **Dragoon**: Innate Ignore Elevation.
- **Mages**: Added Swiftspell, Halve MP, and Magick Defense Boost to relevant classes.
- **Monster HP**: Various monsters buffed (+20-30% HP).

### 🏪 Shop & Skill Changes
- **Rare Items**: Artemis Bow and Holy Lance added to Chapter 4 shops (Lesalia/Riovanes).
- **Ultima**: Buffed Power (23 -> 50) and adjusted MP/CT. **Learnable ONLY on hit (Blue Magic)**, displays as `???` in the JP menu. Not learnable via JP.
- **Mettle**: Expanded with Duskblade and Shadowblade in later chapters.
- **Hasteja**: Nerfed EffectArea (3 -> 2) for balance.
- **JP Costs**: **Halved for all abilities** (except Ultima/Zodiark which are preserved at 9999 for `???` display).

### ⚖️ Difficulty Tuning
- **Tactician**: Enemy PA and Damage reduced (120% -> 115%).
- **Tactician Speed**: Capped enemy speed bonuses for fairer difficulty.

## 🛠️ Technical Details
This mod uses the `fftivc.utility.modloader` framework.
- **XML Edits**: Modifies JobData, ItemData, ItemWeaponData, ItemArmorData, etc.
- **NDX Overrides**: Includes custom `.nxd` tables for JP cost adjustments, ability overrides, and difficulty scaling.

## 📦 Installation
1. Ensure you have [Reloaded-II](https://reloaded-project.github.io/Reloaded-II/) and the [FFTIVC Mod Loader](https://github.com/nenkai/fftivc.utility.modloader) installed.
2. Download or clone this repository.
3. Place the `fftivc.jobs.ramzaoverhaul` folder into your Reloaded-II `Mods` directory.
4. Enable the mod in the Reloaded-II launcher.

## 📜 Credits
- Created for the FFTIVC community.
- Built with support from the FFHacktics wiki and Nenkai's modding tools.
