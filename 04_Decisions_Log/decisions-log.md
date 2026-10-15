---
name: decisions-log
description: Running dated list of decisions John has made. Add a line whenever a decision is locked. AIs should check this before proposing a change of direction.
status: draft
last_reviewed: never
---

# Decisions log

Seeded on 2026-10-15 from Claude's memory. Newest at the bottom. Add new entries using `_Templates/decision-entry.md`. Entries marked LOCKED were described as locked by John at the time.

## Workflow and tools
- **2026-08-05**: Design work stays in pure design mode. If a design hits a real unknown, pause, check real files, record the check, return to design. (Project: general)
- **2026-08-19 (LOCKED)**: Claude is the primary architect and code writer for new LEGAiSEE work. Output as downloadable files, not chat paste. Other tools (Cline, Gemini, local models) are reassigned to a narrow "file survey" role. GPT/Kimi remain backup code generators. Windsurf only for large multi-file builds. (Project: LEGAiSEE)
- **2026-08-20**: FileZilla dropped from the normal workflow. John edits files directly on the server in cPanel's online code editor. (Project: general)
- **2026-08-26 (LOCKED)**: Zip uploads to Claude eliminated (too token-expensive). GitHub repo `LEGAiSEE_Repo` is a manual backup that John pushes at the end of chat sessions. Server is truth, git is backup. (Project: LEGAiSEE)

## LEGAiSEE
- **2026-08-24**: The Master Preface (John's Google Doc bootstrap) adopted verbatim as the canonical process rules. Read order: Preface, current-state, master TOC, then only the files the task needs.
- **2026-08-24**: Sequencing correction. Examine and document EVERY part of the system first; triage decisions are not made cluster-by-cluster.
- **2026-08-30**: Phase 2 triage complete. Every dead or orphaned cluster has a decision.
- **2026-09-01 (standing rule)**: Macro view is never sidelined. V2/V3 items are postponed in execution order only. V1's foundation must support the full future system.
- **2026-09-01**: V1 "done" is redefined: not the Shallow Dig/mini-dig dossier (that is only the lead-magnet entry point). V1 = prospect in, Full Signal Excavation across the 40+ channels, graded artifact evidence, delivered Authority Marketing System, run end to end.
- **2026-09-01**: WO-18 (tree_nodes / identity layer) closed. 9 rows: 3 internal project nodes, 5 active client nodes, 1 archived duplicate.
- **2026-09-06**: WO-19 (wire up the Brain pipeline) closed, pending a funded API key. Confirmed a wrong-direction FileZilla sync reverted files; recovered via full server restore to the 9/5 1 pm backup.
- **2026-09-29**: The Excavator / AI-employee idea is PARKED as a possible future version or add-on. The micro/macro audit, repair and build continue as the priority.
- **2026-10-06**: LEGAiSEE website redesign and the registry questionnaire fix are on hold until the CAMERA cohort (the income project) is finished. Hero stone: fire obsidian.

## CAMERA / ATLAS-TV
- **2026-09 (approx.)**: Book and Workbook are two separate documents with matching chapter numbers (58 workbook chapters, 1:1 with the 58 book chapters). Zoom sessions are a separate document built later from the Curriculum Spec.
- **2026-09 (approx.)**: ATLAS-TV is a full-depth standalone course, on hold until CAMERA is complete and earning. Early GPT TOC discarded.
- **2026-09-30**: The presenter site does not stay on one layout. Layouts can be swapped per chapter.
- **2026-10-08**: The presenter site is for John's live cohort only (not self-paced). Workbook scenes are not wanted in it.
- **2026-10-10 (leaning)**: Live Zoom as 5 days x 2 hours in one week, 10 hours live, hard cap. Pending a timed dry run. Also an in-house version for one company's team.
- **2026-10-10**: Freebuff is the executor for CAMERA script rewrites, under CAMERA_WORK_ORDER_V2.md with hard word budgets and stop gates.

## Brain system
- **2026-10-14**: Build a "brain system": local folder of .md files, opened in Obsidian (free), backed up to a new private repository under the existing GitHub account. No second GitHub account.
