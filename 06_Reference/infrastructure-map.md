---
name: infrastructure-map
description: Where John's websites, apps, server, repos and AI tools live. Names and locations only. No passwords, ever.
status: draft
last_reviewed: never
---

# Infrastructure map

Compiled from Claude's memory on 2026-10-15. **No credentials belong in this file.** Where a secret lives, name only the place.

## Hosting
- **Host:** SureServer, managed through cPanel (panel.s413.sureserver.com). Editing is done in cPanel's online code editor (File Manager editor), pasting code. SSH/terminal is also available through cPanel Terminal.
- **Server software:** PHP 8.3. MySQL 5 and MySQL 8 run side by side. The Songwriter app must connect through the MySQL 8 socket explicitly.
- **Home directory:** `/home/carrmulti/`. A `private/` folder outside the web root holds credential files (name only: `pm_db_credentials.php`). Real passwords live in server config files and John's password manager.

## Websites and apps
| Address | What | Notes |
|---|---|---|
| legaisee.com | Public LEGAiSEE site | Seven pages. Palette and fonts locked: see [[legaisee-website]] |
| legaisee.com/commandcenter/ | LEGAiSEE Command Center (PHP/MySQL app) | Database `carrmulti_legaiseearchive`. Entry point `shell.php`. See [[legaisee-command-center]] |
| johnjobsv2.legaisee.com | JobHunt Command Center | Path `/home/carrmulti/www/johnjobsv2`. `johnjobs.legaisee.com` is dead (500 error). See [[jobhunt-command-center]] |
| songwriter.legaisee.com | Songwriter app | Folder `www/songwriter/`, database `carrmulti_songwriter`. See [[songwriter-app]] |
| realtor.legaisee.com | Test location for CAMERA presenter-site scenes | See [[camera-course]] |
| Portfolio site (index.html) | John's portfolio with YouTube-playlist videos | Reads `carrmultimedia_export.json` and `dfs_export.json`. See [[portfolio-gallery-page]] |

## Code repositories
- **LEGAiSEE_Repo**: https://github.com/carrmultimedia-arch/LEGAiSEE_Repo. A manual backup of the server, pushed by John at the end of chat sessions. May lag the live server.
- **john-brain** (new, private): this vault's backup. See [[SETUP_GUIDE]].

## Channels
- YouTube: @carrmultimedia and @DFSMarketingInc. John has YouTube Data API access (key kept elsewhere).

## AI tools in use (as last recorded)
- Claude (architect, primary), ChatGPT, Gemini (including Google AI Studio free tier and for image rendering of CAMERA visuals), Kimi.
- Coding executors: Windsurf (replaced by Devin on install), Cline in VS Code, GitHub Copilot free tier, freebuff, local model qwen2.5-coder:7b via Ollama (found unreliable for multi-file work).
- LEGAiSEE's own brain pipeline has a Claude API connection (configured); OpenAI and Gemini are scaffolded but unkeyed.

## External APIs mentioned
- Datamuse (rhymes and related words, used by the Songwriter app).
- Anthropic API (planned for Songwriter AI Assist, and used by the LEGAiSEE brain pipeline).
