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
