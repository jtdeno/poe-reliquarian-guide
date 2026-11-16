# Reliquarian HCSSF: publishing reviewed progress

Repository: `jtdeno/poe-reliquarian-guide` (branch `main`).

## Initial publication

Commit these files from this setup package to the repository root:

- `poe_reliquarian_hcssf_guide.html` (read-only dashboard)
- `character-progress.json` (latest reviewed level-21 character state)

The local Windows server already has the public raw URL configured and will retrieve both files. Publishing them is a separate step that requires a GitHub write-capable tool (such as Codex). Standard ChatGPT GitHub read access cannot commit them.

## Subsequent PoB updates

Give Codex the reviewed `character-progress.json` produced in your latest chat, or instruct Codex to modify it from the verified review notes. Update only what evidence supports. Preserve these top-level fields:

`format`, `publishedAt`, `source`, `character`, `stats`, `progress`, `findings`, `skills`, `gear`, `nextActions`.

Required format: `reliquarian-character-progress-v1`.

`progress.completedTaskIds` and `progress.completedPassiveIds` must contain ONLY explicitly verified milestones from your current character. Missing milestones are not assumed incomplete. If a milestone is respec'd or removed from the current character, remove its ID. Never infer passive node names from PoB numeric IDs without a current validated node mapping. For ambiguous campaign progress, set `character.act` to `null`.

Do not commit original PoB exports, account hashes, local notes, local backups, or personally identifying data in the public repo. Preserve filename conventions. Validate JSON, commit to `main`, and verify that the raw JSON URL serves the new content.

## Sample Codex task

> In `jtdeno/poe-reliquarian-guide`, publish our reviewed Reliquarian HCSSF dashboard and `character-progress.json` from the files I provide, on `main`. Validate JSON syntax and confirm the required `format`. Keep notes and raw PoB exports out of the repository. In future, update only the character-progress.json to reflect the HCSSF analysis I supply. Do not mark unknown passive nodes as completed or incomplete.

## Multi-character dashboard: active Warden and archived Reliquarian

As of November 15, 2026 the existing `poe_reliquarian_hcssf_guide.html` is a **single multi-character dashboard**. It defaults to Storm Rain Shock-Stacking Warden, with a top switch to the complete Reliquarian archive. The original filename and `/character-progress.json` endpoint remain unchanged for the configured local Windows server.

The root JSON is intentionally backward-compatible with the original Reliquarian renderer: `format: reliquarian-character-progress-v1`, all historic root fields preserved, plus `archive` metadata and an independent `warden` object (`warden-character-progress-v1`). The Reliquarian HC character died **at level 71 by player report**. Its last reviewed PoB was level 59, so its old stats are intentionally left at level 59. Do not overwrite the archive with the new character's state.

### Publishing a new Warden PoB review

1. Compare against the previous **Warden** verified snapshot, not the historic Reliquarian PoB. Distinguish game-verified facts from hypotheses; prioritize Hardcore defense.
2. Update only `root.warden` fields supported by reviewed evidence (and `publishedAt` when relevant). Preserve the entire archive, Reliquarian root fields, Warden history, unknown values, and the existing HTML layout.
3. Use numeric passive **node IDs as strings** in `warden.progress.completedPassiveIds`; verify each against active `3_30` PoB data and ensure removed/refunded nodes are removed. Verify mastery effect IDs separately. Use IDs in the new guide's task table for `completedTaskIds`; never assume an unchecked item is incomplete.
4. Validate JSON, commit authorized changes to `main`, and verify public raw delivery. Keep raw PoB XML, personal details, hashes, and browser-only notes out of this public repository.
5. GitHub publishing does not guarantee synchronization by the existing Windows local server; report those as separate states.
