---
name: WORKFLOW_ADD_AND_SYNC
description: The repeatable routine for adding new notes to the vault and keeping folder, Obsidian and GitHub in sync.
status: active
last_reviewed: 2026-10-15
---

# Add and sync workflow (repeat every time)

## The three golden rules
1. **The folder on your computer is the master.** Change things only through Obsidian (or the folder). **Never edit on the GitHub website.**
2. **Open, work, sync.** Obsidian pulls when it opens, you work, you sync before you close.
3. **Never copy an old version of the folder over a newer one.** (This is the same kind of mistake as the FileZilla incident of 9/6/26.) If you are not sure which copy is newer, stop and ask.

## Start of a work session (about 30 seconds)
1. Open **Obsidian**. It pulls the latest from GitHub by itself (the "Pull on startup" setting).
2. Glance at the bottom bar. If you see any red error, stop and ask Claude before touching anything.

## Adding something new

### A. Material from an AI chat (the most common case)
1. At the end of a useful chat, ask the AI: **"Write a session log using my template."** (Template: `_Templates/session-log.md`. Paste it into the chat if the AI does not have it.)
2. In Obsidian, press **Ctrl + N**. A new note opens in `05_Inbox_To_Review`.
3. Paste the AI's text in. Name the note `YYYY-MM-DD-topic-session-log` (example: `2026-10-20-camera-session-log`).
4. Read it. Fix anything wrong. Delete anything you do not want.
5. Drag it from the inbox into its proper folder (see `FOLDER_TREE.md`). Session logs go to `04_Decisions_Log/`.
6. If it contains a **decision**, add one line to `04_Decisions_Log/decisions-log.md`.
7. If it changes a project's **status**, update that project's row in `03_Projects/00_Project_Index.md`.
8. Set `status: reviewed` and today's date in `last_reviewed` at the top of the note.

### B. A document you already have (Google Doc, Word file, PDF)
1. Open it. Select all and copy.
2. In Obsidian: **Ctrl + N**, paste. (Pasted text usually comes through as clean text. Headings may need a quick tidy.)
3. Add the header block from `_Templates/note.md` at the very top.
4. Put a line in the note saying where the original lives (for example, "Original: Google Doc 'Johnjobs rev 9-9-26'").
5. Move it to its folder and set the status.
6. Word files and PDFs: ask Claude to convert them to a .md note first, then paste the result.

### C. A new project
1. Right-click `03_Projects` in Obsidian, choose **New folder**, name it `Project-Name`.
2. Copy `_Templates/project-status.md` into it and fill it in.
3. Add a row to `00_Project_Index.md`.

### D. Another AI's memory dump
1. Run the prompt in `08_System_Guides/LLM_DUMP_PROMPT.md` in that AI.
2. Paste the result into a new note in `05_Inbox_To_Review`, named `2026-MM-DD-gpt-memory-dump` (or `gemini`).
3. Leave it there. Review it in a separate sitting: for each claim, keep it, fix it, or delete it. Move the verified pieces into the proper notes.

## Syncing (end of every session)
1. Press **Ctrl + P**. Type `commit-and-sync`. Click **Obsidian Git: Commit-and-sync**.
2. Wait for "Pushed" at the bottom.
3. Done. If you set the 30-minute auto-sync, this is a safety net.

## Monthly check (15 minutes)
1. Empty the inbox.
2. Update `00_Project_Index.md` statuses.
3. Re-read `profile.md` and correct anything that changed.
4. In the GitHub repo, check the latest commit date is recent.
5. Make one offline backup copy (see `MISSED_ITEMS.md`).

## Using more than one computer or device
- Install Obsidian and clone the repo on the second machine (ask Claude for the steps).
- **Always pull before you start and sync before you stop.** Two machines editing the same note without syncing is the one way to get a conflict.
- Phones and iPads: the Obsidian mobile app can open a folder, but Git on mobile is fiddly. Treat the phone as read-only unless you want a longer setup.

## If something goes wrong
- **Red error or "conflict":** stop. Do not click Pull or Push repeatedly. Copy the message and ask Claude.
- **You deleted a note by mistake:** it is in GitHub's history. Ask Claude how to restore it. Do not panic.
- **You pasted a password into a note:** delete it, then **change that password**. Once something has been uploaded to GitHub, deleting the file does not erase it from history.
