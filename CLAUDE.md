# brAIn — shared human/AI memory vault

This repo is an Obsidian vault: a flat-ish folder of plain Markdown notes used as
persistent memory by both the human owner and AI sessions. Treat it as a knowledge
base, not a codebase.

## Conventions

- One note per topic/entity, filename is the title: `Postgres tuning.md`.
- Notes live in area folders (e.g. `PadelReplay/`, `Infra/`): pick the existing
  folder that fits, or create a new area folder for a genuinely new area. Never
  save a note at the vault root unless the owner explicitly asks — the root
  holds only `Home.md`, `Inbox.md`, `*.base` files, and the structural folders.
- Link between notes with Obsidian wikilinks: `[[Postgres tuning]]`. Link liberally;
  a link to a note that doesn't exist yet is fine — it marks something worth writing.
- Optional YAML frontmatter for metadata (`tags`, `created`, `source`). Don't invent
  heavy schemas; plain prose with links beats structure.
- Attachments (images, PDFs) go in `attachments/`, referenced as `![[file.png]]`.
- `sessions/<slug>/` holds per-session working memory: plans, notes, and decision
  logs that AI sessions mirror here from repos/worktrees. The worktree copy stays
  where it is — this is the synced, browsable copy. Raw and unpolished is fine;
  wikilink to topic notes where relevant.
- Session folders are promoted into topic notes only when the owner explicitly
  asks to consolidate — never automatically. Consolidated sessions move to
  `sessions/archive/`.
- A repo/project's knowledge base lives in its own area folder named after it
  (e.g. `PadelReplay/`): an overview note named after the repo plus
  subsystem/concept notes. Sessions working in a repo save their notes there by
  default. Ingested notes are stamped with the commit they describe and are
  updated in place on re-ingest.
- `templates/` holds Obsidian note templates. The `{{title}}`/`{{date}}`
  placeholders are expanded by Obsidian, not by AI — when creating notes, mirror
  a template's structure but write real values, never literal placeholders.
- `*.base` files are Obsidian Bases: database views (YAML) over note frontmatter
  properties. Edit them only deliberately; keep frontmatter properties consistent
  so bases keep working.
- Never edit files under `.obsidian/` — that's Obsidian's own config.

## For AI sessions

- Search before writing: a note on the topic may already exist — update it rather
  than creating a near-duplicate.
- When adding a fact, add wikilinks to related existing notes so the graph stays
  connected.
- Dates: write absolute dates (2026-08-25), never "yesterday" or "last week".
- After changes, commit with a short message describing the knowledge change
  (e.g. "add note on X", "update Y with Z"). Push if a remote exists.
