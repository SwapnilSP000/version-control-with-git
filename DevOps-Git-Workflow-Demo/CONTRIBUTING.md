# Contributing

Thank you for helping improve this repository.

## Branching Guidelines

Use the `dev` branch as the integration branch for active work.
Create feature branches from `dev` using the pattern:

- `feature/<short-description>`
- `release/<version>`
- `hotfix/<short-description>`

Example:

```bash
git switch dev
git checkout -b feature/documentation
```

## Commit Naming

Use concise, descriptive commit messages.
Follow a simple style:

- `feat: add git command reference`
- `docs: improve branching guide`
- `fix: update release process`
- `chore: clean up repository structure`

## Pull Requests

A professional pull request should include:

- Clear title and summary
- Purpose of the change
- Related issue or task reference
- Testing or validation steps
- Any screenshots or examples, if relevant

## Review Process

1. Open a pull request from your feature branch into `dev`.
2. Request at least one reviewer.
3. Wait for feedback and address comments with follow-up commits.
4. When approved, merge into `dev` or `release/*` as appropriate.

## Contribution Workflow

- Keep feature branches small and focused.
- Update documentation when adding or changing content.
- Rebase or merge regularly to keep branches current.
- Avoid force-pushing to shared branches unless necessary.
