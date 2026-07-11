# Workflow

This section explains a standard Git workflow from feature development through release.

## Development Flow

1. Start from `dev`.
2. Create a feature branch.
3. Develop and commit changes locally.
4. Push the feature branch to GitHub.
5. Open a pull request into `dev`.
6. Review and merge after approval.

## Workflow Implementation

```bash
git switch dev
git pull origin dev
git checkout -b feature/workflow-docs
git add .
git commit -m "docs: add workflow implementation guide"
git push origin feature/workflow-docs
```

## Pull Request Process

- Target branch: `dev` for new work
- Include a summary and any testing details
- Use reviewers for quality checks
- Address feedback with follow-up commits

## Release Workflow

1. Finish work on `dev`.
2. Create a release branch from `dev`.
3. Test and update release notes.
4. Merge the release branch into `main`.
5. Tag the release.
6. Merge `main` back into `dev` to keep history aligned.

## Release Branch Configuration

```bash
git switch dev
git pull origin dev
git checkout -b release/v1.0
git push origin release/v1.0
```

## Hotfix Workflow

1. Create a hotfix branch from `main`.
2. Fix the issue.
3. Merge into `main` and `dev`.
4. Tag the hotfix release.

```bash
git switch main
git pull origin main
git checkout -b hotfix/fix-typo
git commit -am "fix: correct typo in docs"
git push origin hotfix/fix-typo
```
