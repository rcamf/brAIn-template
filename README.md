# brAIn template

A starter for a **brAIn**: a personal memory vault that is equally usable by
humans and AI agents.

- Plain Markdown files — no database, no lock-in.
- An [Obsidian](https://obsidian.md) vault — open the folder in Obsidian for
  editing, backlinks, and graph view.
- `[[wikilinks]]` connect notes into a knowledge graph.
- Synced across machines with git.
- `CLAUDE.md` teaches AI agents (e.g. [Claude Code](https://claude.com/claude-code))
  the vault's conventions, so they can read and write your memory safely.

## Getting started

1. Click **Use this template** (or fork) to create your own copy — make it
   **private**, it's your memory.
2. Clone it wherever you like on each of your machines.
3. Set the `BRAIN_VAULT` environment variable to that path (e.g. in `~/.zshrc`):
   `export BRAIN_VAULT="$HOME/path/to/your-brain"`
4. In Obsidian: **Open folder as vault** → the cloned directory.

## Claude Code plugin

The companion plugin adds `/brain:init` (does steps 1–3 for you),
`/brain:remember`, and `/brain:recall` so any Claude Code session can use the
vault as persistent memory:

```
/plugin marketplace add rcamf/claude-plugins
/plugin install brain@rcamf-claude-plugins
```

## Layout

- `Home.md` — entry point; link top-level areas from here.
- `Inbox.md` — quick capture for unsorted notes.
- `attachments/` — images and files, referenced as `![[file.png]]`.
- `sessions/` — per-session working memory mirrored by AI sessions from
  repos/worktrees (plans, notes, decision logs — the worktree copies stay put);
  consolidated into topic notes only on request.
- `templates/` — Obsidian note templates (core Templates plugin is pointed here).
- `Sessions.base` — an Obsidian Base giving a table overview of all session logs.
- `CLAUDE.md` — conventions for AI sessions.
