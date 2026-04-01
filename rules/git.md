# Git

- Freeform commit messages — concise, descriptive, lowercase
- Always create PRs in draft mode: `gh pr create --draft`
- Never amend commits
- Never force-push
- Always pull latest main/master before starting new feature work or creating a new branch
- Prefer `git -C <path>` over `cd`-ing into a repo for one-off git commands
- Run `git add` and `git commit` as separate Bash tool calls — never chain them with `&&` or `;`
- Match commit granularity to the task — bulk-adding new files is one commit, not one per file. Split commits only when changes benefit from independent review or rollback.
