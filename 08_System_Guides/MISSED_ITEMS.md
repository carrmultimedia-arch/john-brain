---
name: MISSED_ITEMS
description: Cautions and extra things worth knowing about running the brain vault: security, backups, accuracy, size, and gaps.
status: active
last_reviewed: 2026-10-15
---

# Things you may have missed

## 1. Keep secrets out (most important)
- Never put passwords, API keys, database logins or tokens in any note. The LEGAiSEE audits found real database passwords sitting in code files more than once. Do not repeat that mistake here.
- Keep those in a password manager. Put only the **name** of where a secret lives in the vault ("DB login: see password manager").
- **Deleting a file from GitHub does not remove it from its history.** If a secret ever gets uploaded, change the password. Deleting is not enough.
- The memory export in this vault was checked: it contains no passwords or keys.

## 2. "Private" is not the same as "encrypted"
- A private GitHub repo is only visible to you and people you invite. It is not end-to-end encrypted. GitHub the company can technically see it.
- When you connect an AI to the repo, that AI company receives what it reads. Check each company's privacy settings (for example, whether chats train their models).
- **Client and prospect names are in the LEGAiSEE notes** (for example, in `legaisee-current-state`). Before real client work, decide whether client names should sit in the vault at all. Safer: use codes like "Client-01" in the vault and keep the real names in the LEGAiSEE database.
- Your plan to move to a larger encrypted server later fits this. Treat the vault as "business-sensitive", not "client-secret".

## 3. The memory dump is a first draft, not the truth
- It came from Claude's memory only. It does not contain what only GPT, Gemini or Kimi know about you.
- Several notes are weeks old. For example, `legaisee-current-state` was last updated 9/9/26, and the job-search notes are from August.
- Some notes are AI-authored proposals, not decisions (the "2026 features" document, the "Authority Engine" doc, the Excavator V1 design). They carry a note saying so. Treat them as ideas.
- **Your first job after setup:** read `profile.md` and the project index and correct them. Those two files steer every AI that reads the vault. Mark them `status: reviewed` when done.

## 4. Source documents that live elsewhere
Claude's memory holds summaries, not your original documents. Gather the originals into the vault (see `06_Reference/GATHER_LIST.md`). Examples: CAMERA's four governing documents, the Master Preface Google Doc, the 8/24 macro-audit reports, the CAMERA production bible.

## 5. Size and focus
- AIs cope better with many small, focused notes than a few giant ones.
- The `Audits` folder is about 160 KB. Never ask an AI to read it all. `00_READ_FIRST.md` already tells AIs to read only what the task needs.
- If a note grows past about 300 lines, split it.

## 6. Backups (do not rely on one copy)
- You have two copies now: your computer and GitHub. That is a good start.
- Once a month, copy the whole **John-Brain** folder to a USB drive or a cloud drive as a zip. This protects you if GitHub access is lost or an account gets locked.
- Do not keep the vault inside a folder that another sync tool (OneDrive, Dropbox, Google Drive) also syncs. Two sync tools on one folder cause conflicts.

## 7. Don't put big media in the vault
- No videos, zips or large image sets. GitHub blocks single files over 100 MB, and big files make syncing slow.
- Put a link in a note to where the media lives (YouTube, Google Drive, the server).

## 8. Plugins: keep it boring
- You only need one: **Obsidian Git**. More plugins mean more things that break.
- Skip fancy graph, AI and "second brain" plugins until the basics have worked for a month.

## 9. How to keep AI chats from drifting
- Start each chat by giving the AI `00_READ_FIRST.md` plus your project note.
- End each chat with "write a session log." This is what keeps the vault alive. Without it, the vault goes stale and you are back to scattered memory.
- If two notes disagree, the AI should ask you. Do not let it quietly pick one.

## 10. Keep your AI tools' own memories on
The vault supplements Claude's and others' built-in memory. It does not replace it. Leave their memory features on; if the vault and an AI's memory disagree, the vault (once reviewed) wins.

## 11. An honest limit
Obsidian and GitHub store and show your notes. They do not make an AI automatically know them. The connection happens when you attach files, paste them, or link the repo to a project in the AI's settings. Plan on that small step at the start of each important chat.

## 12. Later upgrades (not now)
- A self-hosted copy inside LEGAiSEE (your original idea) so AIs can fetch notes from your own server. Worth revisiting once the vault has proven itself for a few months and you know which parts you really use.
- A larger encrypted server when client data requires it.
- A simple script that builds a single "context pack" file from your key notes for AIs with small memory windows.
