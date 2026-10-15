---
name: legaisee-master-system-law
description: LEGAiSEE Master System Law v1.0 — the approved single source of truth governing doc for the whole system end to end (build order, identity layer, client lifecycle, divisions, brain pipeline, public site, command center, doctrine, bugs, v2 list); governs and supersedes ad hoc decisions in [[legaisee-os-vision]] and [[legaisee-command-center]]
sources: [chat]
aliases: [Master System Law, Master Law, Build Table of Contents, Master Law v1.0]
---

> Exported from Claude memory on 2026-10-15. Lines marked [stated] were said directly by John. Treat as a first draft until John reviews it.

- [stated] Delivered "LEGAiSEE Master System Law — The Build Table of Contents, Version 1.0" as the single source of truth for LEGAiSEE's structure end to end. Rule: once approved, work proceeds by opening this doc, finding the next unbuilt or broken item, and building only that. Changes only as bug-fix corrections or explicit deliberate revisions John approves — new ideas become a v2 note, not a mid-build detour. Pipeline: Claude thinks, executor builds, John approves, nobody improvises. Code delivery format: complete replacement files with explicit paths, no patches/diffs/snippets unless John explicitly asks otherwise.
- [stated] Document build order (lower layers built first since upper layers depend on them): I. Business Definition, II. Identity Layer, III. Operation Ladder, IV. System Divisions, V. Intake & Excavation/Brain Pipeline, VI. Public Site, VII. Command Center, VIII. Methodology & Doctrine, IX. Known Issues/Bugs, X. Out of Scope for v1.

## Part I — Business Definition
- [stated] LEGAiSEE = solo-practice luxury B2B consultancy; proprietary methodology "Business Archaeology" — forensic excavation of a company's own institutional history (abandoned assets, proven-but-forgotten positioning, Golden Era patterns) reconstructed into a present-day Authority System. Recovers proven messages, never invents them; grades evidence on a 4-tier confidence scale.
- [stated] Target client: businesses operating 5–10+ years, OR family/generationally owned, OR $30M+ revenue; primarily San Antonio/Austin I-35 corridor. Capacity deliberately capped by design.
- [stated] Core gemstone metaphor (canon across site, methodology, deliverables): Stage 0 Natural Habitat (undiscovered history) → Stage 1 Raw Stone (excavated, uncut) → Stage 2 Cut & Shaped/Lapidary (refined) → Stage 3 Mounted (set into Authority System) → Stage 4 Museum Display (delivered/verified/presented).
- [stated] Bedrock Pledge: every claim excavated or triangulated, never invented (Pillar I); 3-Source Rule — two independent sources or one Tier 1 verified primary (Pillar II); Continuous Verification — new evidence after delivery incorporated via addenda, never hidden (Pillar III).
- [stated] Hierarchy of Truth: Tier 1 Verified Primary, Tier 2 Probable, Tier 3 Plausible, Tier 4 Uncertain. Client-facing confidence label set (canon, used verbatim): VERIFIED / PROBABLE / PLAUSIBLE / UNCERTAIN / UNVERIFIED.

## Part II — Identity Layer (OPEN, current top build priority)
- [stated] Founding mandate: whole system based on a file-tree system, John wants full control of where things are stored. Replaces three fragmented identity schemes (client_id/case_id, brain_id, raw prospect_ingests rows) with one: tree_nodes table.
- [stated] Every client/project/sub-project/item is a row in tree_nodes: node_id (PK), parent_id (nullable FK, null = top-level client), name, node_type (client/project/subproject/item), sort_order, created_at, updated_at. Depth unlimited, never hard-coded.
- [stated] api/tree.php: create, rename, move (re-parent), delete (BLOCKS if node has children, surfaces warning — no silent cascade), get_tree.
- [stated] Migration: CORRECTED (9/1, was stale — see [[legaisee-current-state]]): the real client list is 5 prospects, sourced from prospect_ingests filtered to status='current' — Brad Moore Builders, Faust Hotel, Cowboy Plumbing, Good Ol Rockin Therapy Pllc, and AMD (an earlier duplicate dig under the key "AMD Austin" was found and archived, not deleted). Migration into tree_nodes as top-level client nodes is DONE. prospect_ingests gaining a node_id column (to link dig-run history back to its client node) is still not done.
- [stated] Rule: no new feature/table/pipeline stage may invent its own identity scheme — everything attaches to node_id (intake.php, Brain pipeline, network_add_node.php, search.php all pending rework to key off node_id).

## Part III — Operation Ladder (client lifecycle)
- [stated] Sequence: Lead Generation → Dig Site Surface Scrape (lead magnet) → Shallow Dig $2,500 (Golden Era estimate, 1–3 surfaced assets, competitive gap mapping, one inflection point, excavation brief; delivered live) → Full Signal Excavation (Exhibit A) → Full Institutional Record (Exhibit B) → Institutional Signal Retainer (Exhibit C) → Enterprise Commissions (Enterprise Signal Retainer, The Permanent Record, Exhibit D CAMERA, Private Commissions Exhibits E/F/G).
- [stated] Build requirement: each rung must eventually be a queryable status/milestone on a client's tree node.

## Part IV — System Divisions (access-control concern, not separate codebases; all share tree_nodes)
- [stated] LEGAiSEE Division: excavation/dig/search assistant (40+ channel taxonomy, multi-model search), the Brain/OS (ingests, organizes, connects, analyzes, builds Shallow Dig reports/Dossiers/Dig Reports, suggests strategy), continuous monitoring + Client Portal updates, self-monitoring.
- [stated] Private Division: John's own ingests (personal AI chats, LEGAiSEE growth notes) — same engine, walled off from any client-facing surface.
- [stated] Operations Division ("Legaisee Operations"): CRM, billing, email, and the Client Portal itself.

## Part V — Intake & Brain Pipeline
- [stated] Core defect: none of the nine Brain files (intake.php, search.php variants, brain_start/stream/stream_v4/orchestrator/memory_graph/dossier/state/synthesis.php, network_add_node.php) carry client identity — only file + brain_id. Missing layer, not a one-file bug.
- [stated] Fix (locked): brain_start.php requires + persists node_id in session JSON alongside brain_id; every downstream stage reads node_id from the session (never re-collects from frontend) — mirrors the pattern brain_dossier.php/brain_state.php already use for brain_id lookups.
- [stated] Rebuild order: tree_nodes live → brain_start.php revised → other six brain files revised to read node_id from session → network_add_node.php re-pointed to node_id → intake.php rebuilt as a real form bound to node_id → search.php demoted to secondary filter over the tree.
- [stated] Open question flagged for later: brain_synthesis.php confidence scoring is currently a random placeholder (rand(60,95)) — must be replaced with real Hierarchy-of-Truth-based scoring before any Dossier output reaches a client. Not blocking the identity rebuild.
- [stated] The Master System Law itself, and other governing/spec docs like it, are working Google Docs John has kept through the build and that keep changing as the build progresses — not static. He also has a large volume of LLM chat logs containing similar/overlapping planning info that he wants ingested into the system's Brain/intel layer to be organized and structured into coherent docs/ideas, rather than living scattered across chats.

## Part VI — Public Site (legaisee.com)
- [stated] Seven destinations: index.html (Home), archaeology.html, method.html, serve.html (Industries), practitioner.html ("Exhibit Zero: A Live Reconstruction" — archaeology performed on John himself), commissions.html (Exhibits A–G + CAMERA + Bedrock Pledge), registry.html (confidentiality cells, intake entry point).
- [stated] Locked design tokens: Obsidian #050505 (bg), Gold #C9A961 (accent/CTA), Platinum #EBEBEB (text); fonts Cinzel/Cormorant Garamond/Inter (display/body-serif/UI). Violet is forbidden — remnant of a discarded earlier theme.
- [stated] .card--illumine effect (museum top-light, gold, hover-triggered) is an approved closed spec applied to: Exhibit cards + Bedrock Pledge clauses (commissions.html), three archetype cards (serve.html), Lindy proof cells (archaeology.html), confidentiality cells (registry.html). CSS lives in legaisee-luxury.css.
- [stated] Logo splash: animated SVG intro, ~58 addressable spark points in ~12 groups, three diamond gems + polyhedron as primary ignition points; in production in Affinity Designer/Illustrator (asset task, not code task, until delivered).

## Part VII — Command Center (internal backend, legacy/current)
- [stated] Server: /home/carrmulti/www/www/commandcenter/ — SureServer, MySQL 5.7 Percona, PHP 8.4. DB: carrmulti_legaiseearchive.
- [stated] Locked rules: shell.php is the sole page-rendering routing entry; kernel_db() is the only permitted DB access pattern; ui/global.css is the only permitted stylesheet; AJAX cannot route through shell.php (ob_start buffering) — JSON endpoints must live in api/ and be called directly.
- [stated] Modules built: prospect excavation w/ entity extraction, Dig Review interface, search module (3-column, pending demotion), file manager, ingest module, 18+ file governance/doctrine system.

## Part VIII — Doctrine (canon reference copy, implemented faithfully wherever referenced)
- [stated] Ten Interlocking Frameworks: 40+ Channel Taxonomy (8 evidence classes), 3-Source Rule, Hierarchy of Truth, Triangulation Protocol, Continuous Verification, 8-Dimension Voice Profile, ROI Triggers, Competitive Asymmetry, Private Archaeology Protocol.
- [stated] CAMERA Authority Framework™ (Exhibit D, on commissions.html): Character Positioning, Audience Psychology, Monetization Alignment, Engagement Engineering, Repurposing Infrastructure, AI Acceleration.
- [stated] Pricing ladder (canon): Phase 0 Surface Survey $2,500 · Exhibit A Archaeological Excavation $5,000–$7,500 · Exhibit B The Lapidary $8,500–$18,000 · Exhibit C The Mounting from $4,500/mo · Exhibit D CAMERA $6,500–$7,500 · Exhibit E Master Craftsman's Presence $18,000/mo · Exhibit F Estate & Provenance Appraisal $25,000–$50,000 · Exhibit G Curator's Secret Intelligence $35,000/qtr.

## Part IX — Known Issues (working list, removed only when confirmed fixed)
- [stated] REVISION (8/19, John's own call): Law docs are working reference points, not scripture — explicitly revisable as the system evolves. First confirmed revision: the Authority Marketing System component (turning reviewed Findings into the actual structured client deliverable) was assumed done/covered by report_module.php but is confirmed missing. Reclassified from "v2 polish" to a real v1 gap — client journey should not be run for a real first client until this exists, to avoid discovering missing pieces mid-engagement.
- [stated] Standing near-term priority (8/19): before building anything new, verify the already-built Client View/Drill-In (Timeline/Graph/Findings/Report/Payment/Email) works live end-to-end on one real case — John has not personally seen this run start to finish despite it being marked built.
- [stated] network_add_node.php double-write/double-echo: FIXED this session, pending deployment confirmation.
- [stated] Brain pipeline missing client identity: diagnosed, fix designed (Part V), not yet implemented.
- [stated] intake.php under-built (too few fields, no node binding): OPEN.
- [stated] 2–3 competing search.php UIs: OPEN, to be demoted once tree browsing exists.
- [stated] brain_synthesis.php placeholder scoring (rand(60,95)): OPEN, flagged.
- [stated] No file-tree/node system exists yet: OPEN — Part II is the spec, not yet built.

## Part X — v2 / Deferred (not rejected, just sequenced; needs explicit approval to move up)
- [stated] Long-horizon vision (not v1): once ProjectManager/ is finished as its own clean standalone app, connect it to LEGAiSEE's Brain/decision engine so the engine can author its own work orders directly into ProjectManager (e.g. detecting a needed PHP maintenance/upgrade and creating the task itself) rather than just surfacing findings in a report. Same mechanism extends client-facing: dig-down findings → client portal updates → scheduling, all routed through the same task/milestone spine — ProjectManager, client dig-down, client portal, and scheduling becoming cohesive connected "wings" for both John's own operations and the client engagement, not just internal system upkeep. Explicitly sequenced behind ProjectManager reaching a finished, isolated v1 first — the isolation is what protects this integration from becoming another half-built mid-build detour.
- [stated] Client Portal (full client-facing login, update feed, report access).
- [stated] CRM, billing, email integration inside Legaisee Operations.
- [stated] Self-monitoring/predictive maintenance system.
- [stated] Real multi-model excavation assistant ("4up AI models / 40+ locations" search engine); model_router.php exists but not yet reviewed/specified.
- [stated] Real confidence scoring in brain_synthesis.php to replace placeholder.
- [stated] Animated SVG logo splash integration (asset itself is in production now; integration is v2).

## Appendix B — Server & Path Reference
- [stated] Client tree path (current, pre-Part II): /data/clients/{client_id}/cases/{case_id}/tasks/queue.json. API endpoints: /api/v8/ (called directly, never through shell.php). Brain session files: /data/brains/{brain_id}.json. Brain memory graph: /data/brains/graph.json. Normalized source documents: /normalized/. Public site stylesheets: legaisee.css (base), legaisee-luxury.css (luxury v2.0).
