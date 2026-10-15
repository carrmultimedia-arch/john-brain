---
name: how-to-work-with-john
description: John's standing working preferences and the Architect + Executor pipeline. Read at the start of every session.
status: draft
last_reviewed: never
---

# How to work with John

Source: John's saved preferences and his statements across many sessions with Claude. Dates are when he said it.

## Communication
- **Not a coder.** Explain in plain language. When he must check something (browser, files, server), give exact numbered click-by-click steps. Do not assume he knows words like "DevTools", "Network tab" or "Response body".
- **Terminal commands**: each paste in its own clearly separated, labeled box. A long work order with several commands run together confused him because he could not tell where one ended.
- **Questions**: ask them as plain inline text. Do not use tappable multiple-choice pop-ups. His small screen means they hide the chat and he has to close them to read what they refer to.
- **Wants the AI to do the heavy lifting** (9/30/26): make the design decisions, deliver complete polished work, not minimal steps he has to keep correcting.
- **Token and time waste annoys him** (8/20/26). Chasing a bug file-by-file on an already-working feature was called out. Prefer fast verification methods (search, terminal checks) over long chases.

## The Architect + Executor pipeline
- **Architect**: an AI (currently Claude, locked 8/19/26 as "most trustworthy so far") designs, tracks the project, and writes work orders (WOs) and code.
- **Executor**: another tool writes or applies the code from the work order. Executors John has used: Windsurf (later replaced by Devin on install), Cline in VS Code (local model or Gemini free tier), GPT, Kimi, GitHub Copilot free tier, and "freebuff" (used for CAMERA presenter-site and script work; send it only one or two changes at a time or it redesigns things).
- **Approver**: John reviews and pastes. He edits files directly on the server in cPanel's online code editor (since 8/20/26).
- When giving an executor an instruction, suggest which tool fits it (harder multi-file reasoning vs trivial edit vs large capped build).
- Claude delivers code as a downloaded file, not pasted in chat, to avoid page-splitting and length limits.

## Trust model for code and files
- **Server is truth, git is backup.** The GitHub repo (LEGAiSEE_Repo) is a manual backup that John pushes himself, timed to the end of a chat session. It may lag behind live changes. Never treat a repo copy as proof that an edit landed. Ask him.
- An incident on 9/6/26: a FileZilla sync went the wrong direction and overwrote live files with old local copies. It needed a full server restore. This is why FileZilla was dropped from the normal workflow. **Never sync in the wrong direction. When in doubt, stop and ask.**
- Zip uploads to Claude were eliminated (8/26/26): too token-expensive. Use the GitHub repo or single files instead.

## Method rules (apply to LEGAiSEE and generally)
- Design work stays in pure design mode. If a design hits a real unknown, pause, check the real code or schema, record the check, then return to design. No open-ended exploring, no fixing things found along the way unless asked (8/5/26).
- Work in bounded tasks. One objective per session. Leave a clean continuation point.
- The project files are the persistent memory. Do not reconstruct history from the conversation.
- Do not redesign before the evidence is in. Do not rebuild before checking whether it already exists. Preserve discoveries before changing or removing anything.
- Macro view is never sidelined (9/1/26): postponed items stay visible in the plan; the V1 foundation must support the full future system.

## Session routine
1. Read `00_READ_FIRST.md`, this file, the project index, and the one project John is on.
2. Do one bounded task.
3. At the end: provide a session log (template in `_Templates/session-log.md`) and list the files John should update.

See also: [[dev-workflow]] (full history of tool decisions), [[vault-rules]].
