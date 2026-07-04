# Git Stash Example

Git stash is useful when you need to save local changes temporarily and switch branches.

## Common Stash Commands

- `git stash` — save current changes.
- `git stash list` — show saved stash entries.
- `git stash apply` — reapply the latest stash.
- `git stash pop` — reapply and remove the latest stash.
- `git stash drop` — delete a stash entry.

## Example Scenario

1. You are working in a feature branch and need to review a bug on `main`.
2. Save your work:

```bash
git stash push -m "WIP: update documentation"
```

3. Switch to the bugfix branch:

```bash
git switch main
```

4. After review, return to your feature branch:

```bash
git switch feature/examples
git stash pop
```

## Notes

- Use descriptive stash messages when you create stashes.
- Keep stash usage temporary; avoid long-lived stash stacks.
