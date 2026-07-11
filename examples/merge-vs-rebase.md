# Merge vs Rebase

This example explains the difference between merge and rebase in Git.

## Merge

`git merge` preserves branch history and creates a merge commit when integrating changes.

Example:

```bash
git checkout dev
git merge feature/examples
```

- Pros: preserves true historical context; easier to track how branches combined.
- Cons: more merge commits, which can produce a less linear history.

## Rebase

`git rebase` moves commits from one branch on top of another branch.

Example:

```bash
git checkout feature/examples
git rebase dev
```

- Pros: cleaner, linear history.
- Cons: rewrites history, which should not be done on shared public branches.

## When to use each

- Use `merge` for shared feature integration and release branches.
- Use `rebase` for local cleanup before pushing a feature branch.

## Example workflow

1. Create a feature branch from `dev`.
2. Make commits on the feature branch.
3. Rebase onto `dev` locally to update the branch.
4. Merge into `dev` once ready.
