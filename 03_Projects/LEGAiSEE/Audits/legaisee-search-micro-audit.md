---
name: legaisee-search-micro-audit
description: Function-level micro-audit of the ingested-content search cluster — one real live hybrid search feature, plus an entire earlier-generation "archive search + dual compare" prototype system that's a self-contained dead island
sources: [chat]
aliases: [search micro-audit, archive search deep dive]
---

> Exported from Claude memory on 2026-10-15. Lines marked [stated] were said directly by John. Treat as a first draft until John reviews it.
- [stated] Fifth micro-audit in the sequence (after brain, UI, recommendation, excavation/semantic-diff), going down the 6 rebuild families list per John's instruction — examine/document everything first, no triage or fixing until the whole system is examined
- [stated] Source: commandcenter.zip, read directly via bash/view tools in Claude's sandbox

## STATUS: INVENTORY COMPLETE for this cluster

## The one real, live, mature implementation
- **modules/search_module.php (393 lines)** — registered in kernel/module_registry.php → shell.php sidebar. Genuinely hybrid: scans 4 JSON directories (cases, clients, prospects, network) AND queries 5 real MySQL tables (documents, files, entities, relationships, memory_ingest) in a single search pass. Full three-column UI: result list + two comparison panes (A/B) with client-side find/highlight/navigate (vanilla JS, "lee" prefix naming — leeSearch, leeSelect, leeSetPane, leeFindInPane, etc.).
- **api/search_load.php** — its real live companion, called directly by the module's JS (bypasses shell.php on purpose, per its own comment, because shell.php buffers module output and would break a raw JSON response). Notably well-built: uses realpath() + string-prefix containment checks to prevent path traversal — better security practice than most of what's been found elsewhere in this codebase.

## An entire earlier-generation prototype — a self-contained DEAD ISLAND, zero live callers
All of these operate on a completely different, older data source (normalized/index_meta.json — a flat-file archive index, not MySQL) and confirmed to have **zero inbound references from any live/reachable file**:
- **api/search.php** — basic substring search over normalized/index_meta.json
- **lib/archive_search.php** — a more refined near-duplicate of api/search.php (adds similar_text() percentage scoring on top of substring matching) — genuinely better code than api/search.php, but equally unwired
- **pages/search.php** — a third variant on the same normalized/ data source, already has a primitive A/B dual-pane compare concept (contentA/contentB) — reads as an early prototype of the idea that matured into modules/search_module.php's polished pane system
- **search_dual.php** — orphaned entry point that links to both api/search.php and pages/search.php; requires lib/semantic_diff_engine.php but never calls it — same dead-require pattern already found repeatedly in [[legaisee-brain-micro-audit]]'s fake flat-JSON universe
- **search.phpbak** (731 lines) — has its own large `lee_run_search()` function; the "lee" naming convention matches the LIVE module's client-side JS naming, strongly suggesting this is an earlier full server-side draft that got superseded and renamed to .phpbak (a non-executable extension — can't run as PHP via a normal web request regardless of wiring)
- **test_search.php** — standalone test harness for the old normalized/index_meta.json approach, unrelated to the live MySQL-based module
- **components/nav.php** and **saved_views.php** — both zero-caller orphans, referenced only by this dead search island (not by anything live) — nav.php was already flagged in [[legaisee-ui-micro-audit]] as part of the abandoned root /components/ system; this confirms it specifically belongs to this dead search-prototype generation, not a separate abandoned attempt

## Cross-reference
Both search_dual.php (this cluster) and 6 files in the brain audit's fake flat-JSON universe require lib/semantic_diff_engine.php without ever calling it — reinforcing [[legaisee-excavation-semanticdiff-micro-audit]]'s finding that semantic_diff_engine.php is genuinely good, complete code that's simply never been wired to a real caller anywhere in the codebase.

## STILL TO DO
- Continue down the rebuild-family list per John's instruction — next: ProjectManager/ (last one on the original list)
- All triage/DELETE/KEEP calls for this cluster wait for the single system-wide triage-then-execute pass per [[legaisee-recovery-roadmap]]'s corrected sequencing — nothing gets acted on from this file in isolation
