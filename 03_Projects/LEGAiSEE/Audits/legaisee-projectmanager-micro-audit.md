---
name: legaisee-projectmanager-micro-audit
description: Micro-audit of ProjectManager/ — a self-documenting standalone app with its own governance/Bible system that gives precise build status; found a real naming-mismatch bug and confirms zero UI exists yet
sources: [chat]
aliases: [ProjectManager micro-audit, PM deep dive]
---

> Exported from Claude memory on 2026-10-15. Lines marked [stated] were said directly by John. Treat as a first draft until John reviews it.
- [stated] Sixth and final micro-audit in the original 6-family list (after brain, UI, recommendation, excavation/semantic-diff, search), per John's instruction — examine/document everything first, no triage or fixing until the whole system is examined
- [stated] Source: commandcenter.zip, read directly via bash/view tools in Claude's sandbox

## STATUS: INVENTORY COMPLETE for this cluster (approach differs from the other 5 — see note at bottom)

## What ProjectManager actually is
A standalone application at ProjectManager/ (NOT a shell.php module) — a proper MVC structure (app/Controllers, Models, Repositories, Core, Services, Policies) with its own governed build process modeled on the same discipline LEGAiSEE's overall project now uses: a "Project Manager Bible" of 51 numbered chapter docs (governance/PROJECT_MANAGER_BIBLE/), locked-chapter rules, and its own session-handoff docs. Intended as a full Notion/Asana/Jira-style PM tool, integrated with but separate from the main Command Center.

## Precise build status, established directly from its own two handoff docs (not inferred)
- **Batches 1-6 CONFIRMED COMPLETE and validated** (per governance/PROJECT_MANAGER_BIBLE/LEGAiSEE_PROJECT_MANAGER_HANDOFF_V1.md, dated July 18 2026 — more recent and authoritative than the earlier 0999_SESSION_HANDOFF.md's July 16 note): Governance foundation, ownership/build rules, product definition, database foundation, runtime foundation (bootstrap/router/Core classes), and 12 Models + 12 Repositories (User, Role, Permission, Client, Project, Task, Milestone, Comment, Label, ProjectMember, Attachment, ActivityLog). All validated with real passing PHP test commands against the real production database (same DB as the main Command Center: `carrmulti_legaiseearchive` on mysql.s413.sureserver.com).
- **Batch 7 (Workspace Database Foundation) — STALLED MID-BATCH.** The plan called for migrations 009 (projects) through 014 (project_activity), plus a schema.php update. Only **migration 009_create_projects_table.php exists** — 010-014 (tasks, milestones, comments, notes, project_activity) were never created, and schema.php was never updated to include any of the new tables.
- **REAL BUG FOUND, confirmed by direct file comparison:** TaskRepository.php queries a table called `pm_tasks` (prefixed), but ProjectRepository.php — sitting right next to it, built in the same batch — queries `projects` (unprefixed, matching the actual migration 009 table name). This is a genuine naming-convention inconsistency, not just a missing migration: even after someone writes migration 010, the Task-related code as currently written won't find its table unless the prefix mismatch gets resolved too. Session context suggests this crept in during a later, less disciplined session (per 0999 doc's dated "7-16-26 11:28pm" note describing Controllers/Models/API for Task/Comment/Milestone/Client/Label/ProjectMember being generated in a batch that explicitly flagged itself as having gone off-process: "Stop generating blindly. Audit existing...").
- **Confirmed by direct filesystem check: zero UI exists.** app/Views/, assets/, and app/Components/ are all completely empty — no HTML, no CSS, no JS. This matches what both handoff docs describe as still-pending ("Front-end views, JS API client, Kanban/List UI" were explicitly the next-next steps, never reached).
- **Practical implication:** the Controllers and API endpoints for Task, Milestone, Comment, Label, and ProjectMember (all of which exist as PHP files) are almost certainly non-functional right now if actually invoked, since their underlying database tables were never created and at least one (Task) has a table-name mismatch even in its own code. The Auth/User/Role/Permission layer, by contrast, IS validated and real — that portion has passing tests against the live DB.

## Approach note — differs from the other 5 micro-audits
Unlike brain/UI/recommendation/excavation/search, this cluster was not read file-by-file for every Controller/Model/Repository (there are dozens: full Controllers, Models, Repositories, Core classes, and ~15 api/ subfolders). Instead, this audit relied on ProjectManager's own governance documentation — which is unusually precise and appears reliable — cross-checked with direct spot-checks (table-name grep across TaskRepository.php, ProjectRepository.php, migration 009, and a direct filesystem check of app/Views/assets/Components) that confirmed the docs' claims match the actual code. If a full per-file inventory matching the other 5 clusters' rigor is wanted later, that would need a separate pass — flagged here rather than assumed unnecessary.

## STILL TO DO
- This was the last cluster on the original 6-family list from [[legaisee-recovery-roadmap]] — check whether any other rebuild families remain unexamined system-wide, or whether the "finish examining everything" condition is now met
- If John wants full per-file rigor on ProjectManager matching the other clusters, that's a distinct follow-up task, not yet done
- All triage/DELETE/KEEP/FIX calls for this cluster wait for the single system-wide triage-then-execute pass per [[legaisee-recovery-roadmap]]'s corrected sequencing — nothing gets acted on from this file in isolation
