---
name: FOLDER_TREE
description: The folder structure of the brain vault, what goes in each folder, and where to put new things.
status: active
last_reviewed: 2026-10-15
---

# Folder tree

```
John-Brain/
├── 00_READ_FIRST.md              ← The first file any AI reads. Rules, map, trust levels.
├── .gitignore                    ← Tells Git which Obsidian clutter not to upload.
│
├── 01_About_John/                ← WHO he is. Changes slowly.
│   ├── profile.md                  Consolidated profile. Review this first.
│   ├── production-background.md    33-year career detail
│   ├── music.md                    Musicianship
│   └── recent-work.md              Job-search and current work situation
│
├── 02_Governance/                ← HOW to work with him. Rules, not projects.
│   ├── how-to-work-with-john.md    Communication rules, Architect + Executor pipeline
│   ├── dev-workflow.md             Full history of tool and workflow decisions
│   └── vault-rules.md              Naming, headers, status levels, housekeeping
│
├── 03_Projects/                  ← WHAT he is building. One folder per project.
│   ├── 00_Project_Index.md         One-line status of every project
│   ├── LEGAiSEE/
│   │   ├── 00_Core/                  Preface (rules), current state, master system law,
│   │   │                             master TOC, work orders, recovery roadmap, services
│   │   ├── Vision/                   Where it is going: OS vision, authority engine,
│   │   │                             feature roadmap, excavator, channels, memory concept
│   │   ├── Build/                    Live systems: command center, website, migrations
│   │   └── Audits/                   14 detailed code audits (large; read only as needed)
│   ├── CAMERA-Course/
│   ├── ATLAS-TV/
│   ├── JobHunt/
│   ├── Songwriter-App/
│   ├── Portfolio-Site/
│   └── Brain-System/
│
├── 04_Decisions_Log/             ← WHAT was decided, and when. Append-only history.
│   ├── decisions-log.md            Running list of locked decisions
│   └── (session logs: 2026-10-15-legaisee-session.md, etc.)
│
├── 05_Inbox_To_Review/           ← Landing zone. NOT trusted until John reviews it.
│   │                               Other AIs' memory dumps, new drafts, new notes.
│
├── 06_Reference/                 ← Look-up material, not narrative.
│   ├── glossary.md                 John's terms: Business Archaeology, Exhibit, WO...
│   ├── infrastructure-map.md       Server, domains, repos, tools (no passwords)
│   └── GATHER_LIST.md              Source documents still to bring into the vault
│
├── 07_Archive/                   ← Retired or superseded notes. Almost never read.
│
├── 08_System_Guides/             ← How to run this vault itself.
│   ├── SETUP_GUIDE.md
│   ├── FOLDER_TREE.md              (this file)
│   ├── WORKFLOW_ADD_AND_SYNC.md
│   ├── LLM_DUMP_PROMPT.md          Prompt to pull memory out of GPT, Gemini, etc.
│   └── MISSED_ITEMS.md             Cautions and things worth knowing
│
└── _Templates/                   ← Blank forms for new notes
    ├── note.md
    ├── decision-entry.md
    ├── session-log.md
    └── project-status.md
```

## Where does a new thing go? (decision guide)

| If it is... | It goes in... |
|---|---|
| A fact about John himself | `01_About_John/` |
| A rule for how an AI should behave with him | `02_Governance/` |
| About one project | `03_Projects/<project>/` |
| A decision John just made | Add a line to `04_Decisions_Log/decisions-log.md` **and** update the project note |
| A summary of an AI chat session | `04_Decisions_Log/`, named `YYYY-MM-DD-topic-session-log.md` |
| A new AI memory dump, or anything not yet checked | `05_Inbox_To_Review/` |
| A definition or a fact like a URL | `06_Reference/` |
| Something outdated you do not want to lose | `07_Archive/` |
| A new project | New folder in `03_Projects/`, plus a row in `00_Project_Index.md` |

## Rules of thumb
- Never more than 2 or 3 levels of folders. Deep nesting is hard for AIs and for you.
- If you cannot decide where it goes, put it in the inbox. The inbox is always safe.
- Link notes to each other with `[[note-name]]` instead of copying text between them.
- LEGAiSEE has many notes because the project is large. Other projects start with one status note and grow only when needed.
