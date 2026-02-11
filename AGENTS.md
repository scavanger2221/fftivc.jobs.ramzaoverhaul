# AI Agent Modding Guidelines for FFTIVC

To prevent table conflicts, data corruption, and redundant edits, all AI agents must follow these protocols when modding Final Fantasy Tactics: The Ivalice Chronicles.

## 1. The Master Source of Truth
*   **Database**: `fft_all_data.db` (SQLite) is the master record for all binary changes.
*   **XML Tables**: Files in `FFTIVC/tables/enhanced/` are the source of truth for UI, Job Stats, and Skillsets.
*   **Vanilla Reference**: Use the XML files in `fftivc.utility.modloader/TableData/` to determine original game values. **Never assume a value in the current DB is vanilla.**

## 2. Surgical Database Edits
*   **Avoid Mass Updates**: Never run `UPDATE Table SET X = X * 2`. Always use specific keys or `CASE` statements.
*   **Duplicate Prevention**: Before an `INSERT`, always run `DELETE FROM Table WHERE Key = ID` to avoid fatal errors during NXD export.
*   **Cell Integrity**: Ensure that rows you are not intentionally modding remain set to vanilla values (usually `-1` in override tables) so the mod loader's cell-merging doesn't cause conflicts.

## 3. NXD Export & Maintenance
1.  Apply changes to the master database (`fft_all_data.db`).
2.  Run conversion: `ff16-cli sqlite-to-nxd -i fft_all_data.db -o FFTIVC/data/enhanced/nxd/ -g fft`.
3.  **Preserve existing work**: Ensure that the master database always contains all previous modifications. Regenerating an NXD file should never result in a regression of earlier patches.
4.  **Cleanup**: The export generates many unnecessary files. Keep only the binaries that are part of this mod (e.g., `ability.en.nxd`, `generaljob.nxd`, etc.). Do not delete files that were already present in the mod's `nxd/` folder unless they are no longer needed.

## 4. Verification & Validation
*   **Database Check**: Always verify the state of the database with SQL queries before exporting.
*   **Reverse Export**: Periodically export a generated NXD back to a temporary SQLite file to confirm that the binary data exactly matches the intended modifications.

## 4. XML Formatting Standards
*   **Minimalism**: Only include `<Job>` or `<Ability>` nodes that have actual changes. Remove all original game entries to prevent mod conflicts.
*   **Comments**: Use clear, simple ID labels: `<!-- ID 1: RAMZA CH1 - [Ability Name] -->`. Avoid verbose "fluff" comments.

## 5. Deployment & Sync
*   **Target Folder**: `/home/galkasoft/Desktop/Reloaded-II - FINAL FANTASY TACTICS - The Ivalice Chronicles/Mods/fftivc.jobs.ramzaoverhaul/`
*   **Git**: Commit and push immediately after successful verification of both XML and NXD files.

## 6. Known Mechanics & Edge Cases (What We Learned)

### Formulas & Scaling
*   **Ultima (ID 154)**: Uses **Formula 32**. Setting this in `OverrideAbilityActionData` allows it to scale with PA/MA.
*   **Geomancy (0x0B / 11)**: A hardcoded hybrid formula `Damage = MA * [(PA + 2) / 2]`. **Do not change the Formula ID** for terrain skills; it will break them. Buff via stats or status rates instead.
*   **Physical vs Magical Flags**: `AIBehaviorFlags` in XML must match the intended formula. If a skill uses PA but is flagged as `MagicalAttack`, the AI and multipliers may conflict.
*   **Accuracy**: For status skills (Oracle/Orator), success rate is usually the **Y** column in `OverrideAbilityActionData`.

### Table Nuances
*   **JP Costs**: The `JPCost` in `AbilityData.xml` is **UNUSED** by the game engine. You must edit the `Ability` nex table (exported as `ability.en.nxd`) to change actual costs.
*   **Job Requirements**: Stored in `GeneralJob`. Note that `RequiredJobIds` use **internal indices** (0-based order), not the `Job-en` Keys. 
    *   *Example mapping*: Summoner=11, Orator=14.
*   **Tactician Difficulty**: Enemy stats are controlled via the `DifficultyLevel` table. `UnknownC` = Enemy PA %, `Unknown14` = Enemy Damage %.

### Character-Specific Data
*   **Ramza**: Has three distinct Job IDs (**1, 2, 3**) for different chapters. Always update all three for consistent stat growth.
*   **Stat Growth**: Lower values in `Growth` fields = **Faster** stat gains. Final Chapter jobs usually have lower values than Chapter 1.
*   **Divine Knight**: `Crush Weapon` (162) and `Crush Accessory` (163) lack the `HP` flag by default, meaning they destroy equipment but deal **zero** damage unless modified.
