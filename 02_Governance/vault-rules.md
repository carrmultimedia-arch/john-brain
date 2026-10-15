---
name: vault-rules
description: Naming, header (frontmatter), status levels, and housekeeping rules for the brain vault itself.
status: active
last_reviewed: 2026-10-15
---

# Vault rules

## One idea per note
One file per subject. A fact lives in exactly one place. Other notes link to it with `[[note-name]]` instead of copying it.

## File names
- Lowercase, words joined with hyphens: `camera-course.md`, `legaisee-current-state.md`.
- No spaces, no special characters.
- Dated logs start with the date, year first: `2026-10-15-session-log.md`. This sorts correctly.
- Folders that must stay at the top of a list start with numbers: `00_`, `01_`, `02_`.
- Never rename a note in a file manager. Rename it inside Obsidian so the links that point to it update automatically.

## Header block (frontmatter)
Every note starts with:

```
---
name: the-note-name
description: one line saying what this covers and when to read it
status: draft
last_reviewed: 2026-10-15
---
```

`status` is one of: `draft` (not yet reviewed by John), `reviewed`, `locked` (John's decision, do not reopen), `superseded`.
`last_reviewed` is the date John last confirmed the note is right, or `never`.

## Provenance tags
- `[stated]` John said it directly.
- `[inferred]` An AI concluded it. Needs checking.
- A line should never be tagged `[stated]` unless John actually said it.

## Size
Keep notes under roughly 300 lines where possible. AIs read small, focused notes better than giant ones. The existing LEGAiSEE audit notes are large exceptions. Do not load them all at once.

## What never goes in the vault
- Passwords, API keys, tokens, database logins, bank or card numbers, government ID numbers.
- Large media (video, big image sets, zips). Link to where they live instead.
- Anything John has marked private.

## Where things go
See `08_System_Guides/FOLDER_TREE.md`.

## Review rhythm
- When a note changes, set its `last_reviewed` to the date.
- Once a month, spend 15 minutes on the project index and the status notes of active projects.
- Anything in `05_Inbox_To_Review/` older than 14 days gets moved into its proper folder or deleted.
