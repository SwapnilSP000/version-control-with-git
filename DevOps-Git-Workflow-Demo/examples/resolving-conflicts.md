# Resolving Merge Conflicts

Merge conflicts happen when Git cannot automatically reconcile changes from two branches.

## Common Conflict Workflow

1. Merge or rebase a branch.
2. Git marks conflicts in affected files.
3. Resolve conflicts manually.
4. Stage resolved files.
5. Continue the merge or rebase.

## Example Commands

```bash
git checkout dev
git merge feature/examples
```

If a conflict occurs:

```bash
git status
```

Open files with conflict markers:

```text
<<<<<<< HEAD
current branch changes
=======
incoming branch changes
>>>>>>> feature/examples
```

Resolve the conflict, then stage the file:

```bash
git add <file>
```

Finish the merge:

```bash
git commit
```

If rebasing:

```bash
git rebase --continue
```

## Best Practices

- Review conflict markers carefully.
- Keep each resolved file focused on one logical change.
- Test after resolving conflicts.
