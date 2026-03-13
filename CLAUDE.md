# claude-config

Version-controlled configuration for Claude Code (`~/.claude`).

## Structure

- `global-CLAUDE.md` — global developer instructions, symlinked as `~/.claude/CLAUDE.md` (loaded into every session)
- `rules/` — one markdown file per topic, symlinked as `~/.claude/rules/`
- `settings.json` — permissions, plugins, and feature flags, symlinked as `~/.claude/settings.json`
- `Makefile` — setup automation

## Making changes

- **Add a rule**: create a new `.md` file in `rules/` (one topic per file)
- **Edit permissions or plugins**: modify `settings.json`
- **Edit global instructions**: modify `global-CLAUDE.md`
- Keep `global-CLAUDE.md` concise — it consumes context window in every session
- Rule files should be short and actionable — commands, not prose
- No rule should duplicate what a linter, formatter, or hook already enforces
