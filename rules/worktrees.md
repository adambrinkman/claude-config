# Worktrees

- Prefer worktrees over branch switching for feature work — keeps main checkout clean
- Use `wt switch --create <branch>` to create worktrees
- Use `wt list` to check worktrees and `wt switch` to navigate between them
- Clean up after PR merge: `wt remove <branch>`
- After creating a worktree, `cd` into it as a standalone Bash call before doing any work
- When editing a PR in another repo, `cd` to that repo and run `wt list` to find existing worktrees — don't use `gh pr checkout`
