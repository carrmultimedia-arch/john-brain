---
name: READ_FIRST
type: governance
status: active
last_reviewed: 2026-10-15
---

# READ THIS FIRST: John Carr's Brain System

**If you are an AI (Claude, ChatGPT, Gemini, Kimi, an agent in Cursor/Windsurf/VS Code, or anything else) and you have been pointed at this folder, read this whole file before doing anything else. It is short on purpose.**

## 1. What this is

This folder is John Carr's **brain system**: a set of plain-text Markdown (.md) notes that hold his persistent context. It records who he is, how he likes to work, every active project, the decisions that are already locked, and the rules for working with him.

It exists so that any AI can pick up John's work without him re-explaining everything. **The conversation is temporary. These files are the memory.**

Important: this folder is *storage*, not an intelligence. It does not answer questions or reason. You do the reasoning. Decide what you need, find it here, read it, then think with it.

## 2. Who John is (30 seconds)

John Carr, New Braunfels, Texas. 33-year broadcast and multimedia production veteran (Addy Award, FAA Part 107). Founder of **LEGAiSEE**, a luxury B2B "Business Archaeology" consultancy, and owner of Carr Multimedia. He is **not a coder**. He works as the approver in an "Architect + Executor" pipeline: an AI architects and specifies, other AI tools write or run code, John reviews and approves. Full detail: `01_About_John/profile.md`.

## 3. Rules every AI must follow with John

1. **Plain language.** No jargon without a one-line explanation.
2. **Click-by-click steps** when you ask him to do anything: numbered, exact buttons and menu names. Never assume he knows terms like "DevTools" or "Network tab".
3. **Terminal commands go in their own separate, labeled boxes**, one command per box, so he can see where each begins and ends. Never run several together.
4. **Ask clarifying questions as plain text in the chat.** Do not use pop-up multiple-choice widgets. His screen is small and they hide the conversation.
5. **Do the heavy lifting.** Make the design decisions yourself and deliver complete, polished work. Do not hand him minimal steps to keep correcting.
6. **Macro before micro.** Before fixing the error in front of you, ask why this code is being called, what changed before it, and what was decided earlier. Check this folder for the answer.
7. **Do not rebuild what already exists.** Search the notes (and the code) first. LEGAiSEE has been rebuilt from scratch in several places already.
8. **Never delete based on "orphaned" alone.** Disconnected is not useless.
9. **Server is truth, git is backup** (for code). For this vault the **local folder is truth**, GitHub is the backup copy. Never treat a GitHub copy as proof that a change just made on the server or the computer took effect. Ask John.
10. **No secrets in the vault, ever.** If John pastes a password, key or token into a chat, tell him to change it.
11. **Say what you don't know.** If a note is old or marked draft, say so rather than guessing.
12. **Keep token use low.** Work in bounded tasks. Do not ask for whole zips or whole folders when one file will do.

More detail: `02_Governance/how-to-work-with-john.md`.

## 4. How to read the notes (trust levels)

- Every note has a header block (frontmatter) with `status` and `last_reviewed`.
  - `status: draft` means exported or written by an AI and **not yet reviewed by John**. Useful, but verify.
  - `status: reviewed` means John read it and it is believed accurate as of `last_reviewed`.
  - `status: locked` means John made a decision. **Do not reopen it without asking him.**
  - `status: superseded` means look at the note it points to instead.
- Lines tagged **[stated]** were said by John directly. Lines tagged **[inferred]** were concluded by an AI and need checking.
- Notes that disagree: the one with the **later date** wins, unless one is `locked`.
- The notes exported from Claude's memory on 2026-10-15 are all `draft` until John reviews them. Some are weeks old. Project status moves fast.

## 5. Where to look (map)

| Folder | What is in it | Read when |
|---|---|---|
| `00_READ_FIRST.md` | This file | Always, first |
| `01_About_John/` | Profile, career, music, current situation | Start of any session |
| `02_Governance/` | How to work with John, session rules, vault rules, workflow history | Start of any session |
| `03_Projects/` | One folder per project. `00_Project_Index.md` lists them all with status | When working on a project |
| `04_Decisions_Log/` | Dated log of locked decisions and session summaries | Before proposing a change of direction |
| `05_Inbox_To_Review/` | Unreviewed material (other AIs' memory dumps, new drafts) | Only if John asks. It is NOT trusted |
| `06_Reference/` | Glossary of John's terms, infrastructure map | When a term or system is unfamiliar |
| `07_Archive/` | Retired or superseded material | Almost never |
| `08_System_Guides/` | Setup, sync workflow, templates for maintaining this vault | When maintaining the vault |

## 6. Reading order for a normal work session

1. This file.
2. `01_About_John/profile.md` and `02_Governance/how-to-work-with-john.md`.
3. `03_Projects/00_Project_Index.md`, then the project John is working on.
4. For LEGAiSEE: `03_Projects/LEGAiSEE/00_Core/legaisee-preface.md` first, then `legaisee-current-state.md`. Only then the specific audit or code notes the task needs. **The audits folder is very large. Do not load it all.**
5. `04_Decisions_Log/decisions-log.md` if the task could change direction.

## 7. Projects in one line each

- **LEGAiSEE**: luxury B2B Business Archaeology consultancy plus the PHP/MySQL Command Center software behind it.
- **CAMERA**: media/content creation course (book, workbook, live cohort, presenter site). Income project, currently the priority.
- **ATLAS-TV**: planned authority-marketing course. On hold until CAMERA is finished.
- **JobHunt Command Center**: John's own job-application dashboard.
- **Songwriter app**: self-hosted songwriting and setlist tool.
- **Portfolio site**: John's portfolio with video playlists and a planned stills gallery.
- **Brain system**: this vault.

## 8. Writing back to the vault

- **Do not silently rewrite existing notes.** Propose changes in the chat, or put a new draft in `05_Inbox_To_Review/` using the templates in `_Templates/`.
- At the end of a work session, offer John a **session log** (template: `_Templates/session-log.md`) containing: what was done, what was decided, what is unresolved, and the next task. He saves it into `04_Decisions_Log/`.
- When a project's status changes, remind him to update `03_Projects/00_Project_Index.md` and the project's own status note.
- Use the file naming rules in `02_Governance/vault-rules.md`.

## 9. Privacy

This vault contains John's business-sensitive material, including LEGAiSEE client and prospect names. Use it to help John. Do not repeat it elsewhere, quote it publicly, or send it to third-party services unless he asks. It lives in a private GitHub repository. It must never contain passwords, API keys or database logins.

## 10. If something here seems wrong

Tell John, plainly, what looks wrong and which file it is in. He decides.
