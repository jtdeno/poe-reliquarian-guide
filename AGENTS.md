# PoE 1 HCSSF dashboard maintenance

Read CODEX_PUBLISHING.md before editing or publishing. Preserve the existing schema and filename conventions.

On each uploaded Path of Building XML:
- Compare the active current-character tree, gear, skills, configuration and exported statistics against the immediately preceding verified snapshot. Distinguish current allocations from alternative or planned trees and item sets.
- Prioritize Hardcore survivability and urgent defensive gaps over damage. Distinguish exported values, calculations, user confirmations and recommendations. Keep unknown values unknown.
- Update character-progress.json with evidence-supported changes and source provenance. Preserve comparison history and user notes. Do not infer current act from level.
- Mark a named passive complete only after verifying its exact allocated ID against matching tree-version data. Verify mastery effect IDs separately. Account for refunds. Never infer completion from level, proximity, route plans or another milestone.
- Ensure checkpoint labels match verified node identities before marking completion. Keep unknown checkpoints unverified rather than asserting they are unallocated.
- Give precise next-node instructions only when node identities and adjacency are verified against matching tree data. Otherwise label the route unverified.
- Validate JSON format and dashboard compatibility, then commit authorized changes to main. Publish related HTML and JSON corrections together. Preserve concurrent edits; never force-push.
- Verify public raw content serves the committed revision. Report repository publication separately from the user's local Windows server sync, which cannot be assumed successful remotely.
- Keep original XML exports, account/character hashes, personal notes and local backups out of this public repository as required by CODEX_PUBLISHING.md.

## Multiple characters (3.30 onward)

The original local dashboard filename is retained: `poe_reliquarian_hcssf_guide.html`. It is now the shared HCSSF companion with a default-active **Storm Rain Warden** and read-only **Reliquarian archive**, selected using the top-level build switch. Do not create a second app or delete old sections. Both builds read the existing `character-progress.json`.

- The JSON root remains `format: reliquarian-character-progress-v1` and preserves the historical Reliquarian records, comparison history, and the `archive` object. The archived Reliquarian **died at level 71** by player report, but the last reviewed PoB XML snapshot was **level 59**; never reinterpret its level-59 stats as level-71 data. Root `character.status` is `deceased` and `character.deathLevel` is `71`.
- The independent active character lives at `root.warden`, with `format: warden-character-progress-v1`. Warden has independent `character`, `source`, `stats`, `progress`, `findings`, `skills`, `gear`, and `nextActions`. Do not mix character data or completion flags between builds.
- The Warden plan references the Community PoB `3_30` tree. `warden.progress.completedPassiveIds` contains only confirmed **numeric node IDs as strings** from an active current Warden PoB; verify mastery IDs and effects separately. `completedTaskIds` contains only evidence-backed Warden checklist IDs from the HTML guide. Treat unknowns as unverified, not incomplete.
- Warden is original and **experimental**: 50 Oath of Spring shocks is a maximum, not established sustained boss DPS. Validate beam hits, real shock uptime and defensive maximum hits before endorsing difficult content. Prioritize HC defenses over damage.
- The old and new personal notes use separate browser localStorage keys, not GitHub. Never copy or expose personal notes into public repository files.
- Keep the original filename and root JSON endpoint so the local Windows server can sync both without changing its configuration. GitHub commits do not guarantee the user's local sync succeeded; verify local update state separately if possible.


## Warden full campaign passive plan (3.30)

The Warden's original guide now includes **93 planned regular passives** through Act 10, with exact node IDs, a numbered route and separate per-act targets. The same ordered expectations are stored in `character-progress.json` under `warden.plan.actMilestones`, and displayed in the existing HTML on the Overview, Campaign and Passive Tree tabs. Preserve consistency across both files when editing this route; these are PLAN values only.

- Act-end cumulative targets: **13 / 25 / 40 / 48 / 56 / 66 / 74 / 80 / 85 / 93** (Acts 1–10). This assumes approximately level 70, 24 quest passives and killing all bandits; actual reward timing and levels vary.
- Early conditional keystone **Precise Technique 63620**: use only if Accuracy Rating exceeds Maximum Life. If false, defer or refund; no claim of always-on 40% more attack damage.
- Mastery node/effect expectations: **3042/47642** (+30 Life); **6427/56951** (projectile-speed scaling for bows); **20730/45317** (Lucky suppression, later **58447** at 100%); **50757/57074** (+15% suppression conditional on evasion across four armour slots). Do not mark any mastery selection verified without exact effect ID evidence.
- Current Warden confirmations are kept in `warden.progress.completedPassiveIds`, `completedMasteryEffects`, and `completedTaskIds`. The planned node IDs under `warden.plan` must never be copied into those completion fields unless verified against a current-character 3_30 PoB export.
- Preserve archive data and current local server filenames. The existing app has not become a new separate app.
