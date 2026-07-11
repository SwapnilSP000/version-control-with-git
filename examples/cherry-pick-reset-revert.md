# Cherry Pick, Reset, and Revert

This example covers three useful Git commands for managing commit history.

## Cherry Pick

`git cherry-pick` applies a specific commit from another branch.

Example:

```bash
git switch dev
git cherry-pick <commit-hash>
```

Use cases:
- Apply a bug fix from one branch to another.
- Port a specific change without merging the entire branch.

## Reset

`git reset` changes the current branch HEAD and staging area.

- `git reset --soft <commit>` — move HEAD, keep changes staged.
- `git reset --mixed <commit>` — move HEAD, keep changes in the working tree.
- `git reset --hard <commit>` — reset HEAD and working tree.

Use carefully; `git reset --hard` can discard work permanently.

## Revert

`git revert` creates a new commit that undoes a previous commit.

Example:

```bash
git revert <commit-hash>
```

Use cases:
- Undo a commit on a shared branch safely.
- Preserve repository history while reversing changes.

## Practical Notes

- Use `revert` on public branches to avoid rewriting shared history.
- Use `reset` for local cleanup before publishing changes.
- Use `cherry-pick` to copy a single commit into another branch without a full merge.
