# Tooling

- Python: use `uv` for project/package management and `uv run` to run scripts
- Use built-in tools for all file operations — never fall back to shell equivalents:
  - **Read** not `cat`, `head`, `tail`, `sed -n` — use `offset`/`limit` params to read specific line ranges
  - **Glob** not `find`, `ls`
  - **Grep** not `grep`, `rg`, `awk`
  - **Edit** not `sed`, `awk`
  - **Write** not `echo >`, `cat <<EOF`
- Never chain `cd` with other commands using `&&` or `;`
- Never use command substitution (`$(...)` or backticks) in Bash tool calls — capture the output in a prior step and use it directly, or use built-in tools
- Use LSP diagnostics and go-to-definition to understand code — don't guess at types or imports by grepping
- Grafana: always use the Grafana MCP server tools for querying dashboards, logs, metrics, alerts, and incidents — never curl or WebFetch the Grafana web UI
