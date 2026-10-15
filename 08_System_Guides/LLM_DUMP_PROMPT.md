---
name: LLM_DUMP_PROMPT
description: A prompt to paste into ChatGPT, Gemini, Kimi or any AI to pull out what it knows about John, as a reviewable draft.
status: active
last_reviewed: 2026-10-15
---

# Prompt: get another AI's memory of you

## How to use
1. Open the AI (ChatGPT, Gemini, Kimi, etc.), ideally with its memory/history features on.
2. Paste everything inside the box below as one message.
3. If the answer is cut off, type: `Continue exactly where you stopped.`
4. Copy the result into a new note in `05_Inbox_To_Review`, named `2026-MM-DD-gpt-memory-dump` (or `gemini`, `kimi`).
5. Review it later. Nothing from it goes into the main vault until you have checked it.

## The prompt (copy everything in the box)

```
I am building a personal knowledge vault of plain Markdown notes so that any AI can understand me and my projects. I need you to export everything you know or remember about me, from your saved memory AND from our past conversations.

RULES
1. Do not invent anything. If you are not sure, say so.
2. Tag EVERY line with one of:
   [SAID] = I told you this directly.
   [INFERRED] = you concluded it from context.
   [UNSURE] = you may be misremembering.
3. Include dates (or approximate dates) wherever you can.
4. Do not include passwords, API keys, tokens, or financial account numbers. If I shared any in a chat, write "[secret omitted]".
5. Be complete rather than brief. Long is fine.
6. Output plain Markdown. Use the headings below exactly.

HEADINGS
# About me
Who I am, where I live, career, skills, background, hobbies, how I work.
# How I like to work with AI
My communication preferences, rules I have given you, things that annoyed me.
# Projects
One section per project: ## Project name, then: what it is, goals, current status, key decisions (with dates), open problems, files/tools/websites involved, next steps.
# People and businesses
Relevant people, clients, companies, and my relationship to each.
# Tools, accounts and systems
Software, hosting, services, and workflows I use (no secrets).
# Decisions I have made
A dated list of decisions I made, and why.
# Open questions and unfinished work
Things we left hanging.
# Things you are not sure about
Anything that contradicts itself or that you may have wrong.

At the very end, list the 10 most important things for a new AI to know about me.
```

## After you have the dumps
- Make one note per AI. Do not merge them.
- Read each one. Cross out wrong lines. Where two AIs disagree, you decide.
- Move the confirmed facts into the proper notes in `01_About_John`, `02_Governance` or `03_Projects`, and set those notes to `status: reviewed`.
- Delete or archive the raw dump when you are done.

## For a full history instead of a summary
ChatGPT, Gemini and Claude each have a data-export option in their settings. It gives you every past conversation. These files are very large and should **not** go straight into the vault. Keep them in a separate folder on your computer and ask an AI to pull specific topics from them when needed.
