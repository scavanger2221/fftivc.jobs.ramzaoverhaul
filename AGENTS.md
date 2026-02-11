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

## 3. NXD Export & Cleanup Workflow
1.  Apply changes to `fft_all_data.db` via SQLite.
2.  Run conversion: `ff16-cli sqlite-to-nxd -i fft_all_data.db -o FFTIVC/data/enhanced/nxd/ -g fft`.
3.  **Mandatory Cleanup**: The export generates 240+ files. You **MUST** delete all files except the ones containing active mod data.
    *   *Permissible Files*: `ability.en.nxd`, `generaljob.nxd`, `overrideabilityactiondata.nxd`, `overrideentrydata.nxd`, `difficultylevel.nxd`.
4.  Verify content: Export the generated NXD back to a temp SQLite file to ensure the values are correct before deployment.

## 4. XML Formatting Standards
*   **Minimalism**: Only include `<Job>` or `<Ability>` nodes that have actual changes. Remove all original game entries to prevent mod conflicts.
*   **Comments**: Use clear, simple ID labels: `<!-- ID 1: RAMZA CH1 - [Ability Name] -->`. Avoid verbose "fluff" comments.

## 5. Deployment & Sync
*   **Target Folder**: `/home/galkasoft/Desktop/Reloaded-II - FINAL FANTASY TACTICS - The Ivalice Chronicles/Mods/fftivc.jobs.ramzaoverhaul/`
*   **Git**: Commit and push immediately after successful verification of both XML and NXD files.
