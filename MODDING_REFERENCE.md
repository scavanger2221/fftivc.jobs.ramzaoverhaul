# FFTIVC Modding Technical Reference

This document serves as a technical map for the Final Fantasy Tactics: The Ivalice Chronicles (FFTIVC) mod files and database structures.

## ⚖️ Difficulty Scaling (`DifficultyLevel` table)
Mapping for the 4 primary scaling columns in the database:

| ID | Name | `Unknown8` (Player PA/MA) | `Unknown10` (Arithmeticks) | `UnknownC` (Enemy PA) | `Unknown14` (Enemy Damage) |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **0** | **Knight** | 100% | 100% | 100% | 100% |
| **1** | **Squire** | 110% | 110% | 50% | 50% |
| **2** | **Tactician**| **85%** | **35%** | **120%** | **120%** |

---

## 🎭 Unit Overrides (`OverrideEntryData` table)
Story units use arrays of 3 values following the order: **`[ Knight, Squire, Tactician ]`**

### **Mapping for "Unknown" Arrays:**
- **`Unknown5C`**: **HP Growth Change** (Lower value = Faster HP gain).
- **`Unknown64`**: **HP Multiplier Change** (Flat or % adjustment to base HP).
- **`Unknown6C`**: **Speed Growth Change** (Lower value = Faster Speed gain).
- **`Unknown74`**: **Speed Multiplier Change** (Flat or % adjustment to base Speed).

---

## 🛠️ Tooling & Workflow
1.  **Master Database**: `fft_all_data.db` (SQLite).
2.  **Binary Conversion**: Use `ff16-cli` for conversion.
    - `nxd-to-sqlite`: Binary -> DB
    - `sqlite-to-nxd`: DB -> Binary
3.  **Deployment**: Modded `.nxd` files must be placed in `FFTIVC/data/enhanced/nxd/`.
4.  **Version Control**: Always use `git status` and `git restore` before manual deletion of files.

---

## ⚔️ Key IDs
- **Ramza Jobs**: 25 (Ch 1), 26 (Ch 2-3), 27 (Ch 4).
- **Wiegraf (Riovanes)**: Scenario ID `429`, Unit Index `1`, Spriteset `25`.
- **Belias**: Scenario ID `421`, Unit Index `1`, Spriteset `48`.
- **Arithmeticks Multiplier**: Found in `DifficultyLevel` -> `Unknown10`.
