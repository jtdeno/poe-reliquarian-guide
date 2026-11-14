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
