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

### 🔓 Job Unlock Requirements
- **Bard**: Requires Chemist(2), White Mage(3), Black Mage(3), Time Mage(3), Summoner(3), Orator(3), Mystic(3) - Summoner and Orator halved from vanilla.
- **Dancer**: Requires Squire(2), Knight(3), Archer(3), Monk(3), Thief(3), Geomancer(3), Dragoon(3) - Geomancer and Dragoon added for thematic consistency.
- **Mime**: All job requirements halved for earlier access (Squire 4, Chemist 4, Knight 3, Archer 3, Monk 2, White Mage 3, Black Mage 3, Time Mage 2, Summoner 2, Thief 3, Orator 2, Mystic 3, Geomancer 2, Dragoon 2).

### 🏪 Shop & Skill Changes
- **Rare Items**: Artemis Bow and Holy Lance added to Chapter 4 shops (Lesalia/Riovanes).
- **Mettle**: Expanded with Duskblade and Shadowblade in later chapters.
- **JP Costs**: **Halved for all abilities** (except Ultima/Zodiark which are preserved at 9999 for `???` display).

### ⚡ Spell & Ability Modifications

#### Squire Skills
- **Rush**: 0 MP, Instant Cast (was vanilla values)
- **Throw Stone**: 0 MP, Instant Cast (was vanilla values)

#### White Magic
- **Protect**: CT 3 (faster casting)
- **Shell**: CT 3 (faster casting)
- **Curaja**: Range 4, EffectArea 2 (AoE heal)
- **Protectja**: Range 4, EffectArea 2 (nerfed from vanilla)
- **Shellja**: Range 4, EffectArea 2 (nerfed from vanilla)

#### Time Magic
- **Hasteja**: Range 4, EffectArea 2 (nerfed from vanilla)
- **Slowja**: Range 4, EffectArea 2 (nerfed from vanilla)

#### Black Magic
- **Firaja/Thundaja/Blizzaja**: X 36 (+20% damage)
- **Flare**: X 48 (damage buff)
- **Meteor**: 40 MP, CT 8 (was vanilla)

#### Summons
- **Shiva/Ramuh/Ifrit**: CT 4
- **Titan**: CT 5
- **Golem**: CT 3
- **Carbuncle**: CT 4
- **Bahamut**: CT 7
- **Odin/Leviathan/Salamander**: CT 6
- **Sylph/Faerie**: CT 4
- **Lich**: 50 MP
- **Cyclops**: CT 6
- **Zodiark**: CT 10

#### Mystic/Oracle Skills
All status spells receive +20 accuracy (Y values increased):
- **Umbra**: 220 accuracy
- **Empowerment/Belief/Disbelief**: 170 accuracy
- **Invigoration/Quiescence/Delirium/Harmony/Hesitation/Repose**: 190 accuracy
- **Fervor/Trepidation**: 160 accuracy
- **Corruption/Induration**: 140 accuracy

#### Ultima
- **Power**: 50 (was 23)
- **MP Cost**: 15
- **CT**: 4
- **Formula**: 32 (PA/MA scaling)
- **X**: 34, **Y**: 32
- **Learnable ONLY on hit (Blue Magic)**, displays as `???` in the JP menu

#### Enemy Skills (Sap)
- **Magicksap/Speedsap/Powersap/Mindsap**: 0 MP, Instant Cast

#### Cloud Limit Breaks
- **Braver**: CT 2
- **Cross Slash**: CT 3
- **Blade Burst**: CT 4
- **Meteorain**: CT 6
- **Finishing Touch**: CT 4
- **Omnislash**: CT 7
- **Cherry Blossom**: CT 10

### ⚖️ Difficulty Tuning
- **Tactician**: Enemy PA and Damage reduced (120% -> 115%).
- **Tactician Speed**: Capped enemy speed bonuses for fairer difficulty.

## 🛠️ Technical Details
This mod uses the `fftivc.utility.modloader` framework.
- **XML Edits**: Modifies JobData, ItemData, ItemWeaponData, ItemArmorData, AbilityData, etc.
- **NXD Overrides**: Includes custom `.nxd` tables for ability action data overrides (MP costs, CT, damage, accuracy) and difficulty scaling.

## 📦 Installation
1. Ensure you have [Reloaded-II](https://reloaded-project.github.io/Reloaded-II/) and the [FFTIVC Mod Loader](https://github.com/nenkai/fftivc.utility.modloader) installed.
2. Download or clone this repository.
3. Place the `fftivc.jobs.ramzaoverhaul` folder into your Reloaded-II `Mods` directory.
4. Enable the mod in the Reloaded-II launcher.

## 📜 Credits
- Created for the FFTIVC community.
- Built with support from the FFHacktics wiki and Nenkai's modding tools.
