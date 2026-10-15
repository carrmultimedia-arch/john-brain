---
name: songwriter-app
description: Self-hosted PHP/MySQL songwriting app at songwriter.legaisee.com replacing Songwriter's Pad, growing into a live-performance/setlist tool
sources: [chat]
aliases: [Songwriter's Pad clone, songwriter subdomain]
---

> Exported from Claude memory on 2026-10-15. Lines marked [stated] were said directly by John. Treat as a first draft until John reviews it.

- [stated] Building a self-hosted clone/evolution of Songwriter's Pad (songwriterspad.com) because that product is reaching end-of-life
- [stated] Lives at songwriter.legaisee.com, its own subdomain, fully separate from [[legaisee-command-center]] and the legaisee.com public site
- [stated] Server folder www/songwriter/, PHP 8.3, database carrmulti_songwriter on the server's MySQL 8 engine (server runs MySQL 5 and MySQL 8 side by side; must connect via the MySQL 8 socket explicitly, not plain localhost)
- [stated] Stack: plain PHP + vanilla JS/CSS, no framework, pasted into cPanel's editor or written via SSH terminal (terminal proved more reliable than the visual editor, which introduced hidden/smart-quote characters twice)
- [stated] Single user (John only), mobile/iPad-first design, wants it installable as a PWA (Add to Home Screen)
- [stated] Core original-scope features: Songs (list/create/rename/delete), Blocks (verses/chorus etc. with inline [Chord] tags, continuous-page layout matching the original app's look, not boxed cards), Ideas scratchpad, Chords reference, Rhymes (Datamuse API, also covers thesaurus/related-words)
- [stated] Scope grew to include live-performance tools inspired by Set List Maker (setlistmaker.com) and EasyPerformer: song metadata (Artist/Key/Tempo), sortable/custom-drag song list, Setlists built from the song library, a Performance Mode with an EasyPerformer-style pad-grid song nav (large tap targets, not a thin list, for on-stage use while playing guitar), live chord transpose via up/down arrows, and per-song backing-track audio upload/playback
- [stated] Explicitly decided against MIDI triggers/hardware control (no longer owns MIDI/keyboard gear)
- [stated] Decided project does not need formal governance/audit-tracking docs yet (unlike [[legaisee-master-system-law]]) since it's single-user and single-session-thread; a living PROJECT_STATUS.md is enough for now
- [stated] AI Assist (lyric/idea generation via Claude API) is planned but deferred; will use John's own Anthropic API key with real per-call cost
- [stated] Has a Songwriter App Work Order doc (8 remaining steps: Ideas tab, Chords reference, Rhymes/Thesaurus, Setlists data layer, Performance Mode, Audio playback, PWA polish, AI Assist); shared it 2026-09-21 to resume work; opens new sessions with "Continuing the Songwriter app work order - we left off at Step N"
- [stated] Work order Steps 1-4 finished and confirmed working as of 2026-09-21: Ideas tab (assets/ideas.js, api/ideas_*.php), Chords reference chart (assets/chords.js), Rhymes/related-words via Datamuse (assets/rhymes.js, api/word_lookup.php), and Setlists (assets/setlists.js, api/setlists_*.php + api/setlist_songs_*.php, new setlists/setlist_songs DB tables) — all added without touching the original app.js, each wired into index.php with a backup made first. Step 5 (Performance Mode) core built and working as of 2026-09-21: assets/performance.js — a resizable (drag-corner) song button grid replacing the original plan's fixed sidebar, chord-highlighted read-only lyrics pane, live transpose via +/- buttons, Perform button added to setlists.js, new panel-perform section in index.php. Mobile drawer version (\u2630 button) built but not yet tested on an actual phone. Not yet done: Steps 6-8 (audio playback, PWA polish, AI Assist).
