# claude-config

Version-controlled configuration for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (`~/.claude`).

## How it works

Claude Code reads its global config from `~/.claude/`. Instead of editing files there directly, this repo is the source of truth — `make link` symlinks everything into place so changes are version-controlled.

## Structure

- `global-CLAUDE.md` — global developer instructions, symlinked as `~/.claude/CLAUDE.md` (loaded into every session)
- `rules/` — one markdown file per topic, symlinked as `~/.claude/rules/`
- `settings.json` — permissions, plugins, and feature flags, symlinked as `~/.claude/settings.json`
- `Makefile` — setup automation

## Setup

```bash
make link
```

Symlinks all config files to `~/.claude/`. Refuses to overwrite existing files — remove them first if re-linking.

To remove symlinks:

```bash
make unlink
```

## Making changes

- **Add a rule**: create a new `.md` file in `rules/` (one topic per file)
- **Edit permissions or plugins**: modify `settings.json`
- **Edit global instructions**: modify `global-CLAUDE.md`
- Changes take effect in the next Claude Code session

## Conventions

- Keep `global-CLAUDE.md` concise — it consumes context window in every session
- Rule files should be short and actionable — commands, not prose
- No rule should duplicate what a linter, formatter, or hook already enforces
