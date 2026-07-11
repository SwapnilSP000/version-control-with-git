# Git Best Practices Guide

This document outlines the standard Git hygiene, branch management, commit format rules, and security guidelines used throughout this project to maintain repository integrity.

---

## 1. Commit Hygiene (Conventional Commits)

Clean commit logs make version histories readable and ease releases. We follow the **Conventional Commits** specification:

### Format
```text
<type>(<scope>): <short summary>

[optional body description]

[optional footer(s)]
```

### Commit Types
*   `feat`: Adding a new feature (e.g., `feat(jenkins): add test coverage reporting`).
*   `fix`: Fixing a bug (e.g., `fix(setup): correct environment script paths`).
*   `docs`: Documentation only changes (e.g., `docs(readme): update CI/CD badges`).
*   `style`: Code style updates (formatting, missing semi-colons, no logic changes).
*   `refactor`: Code changes that neither fix a bug nor add a feature.
*   `chore`: Tooling, build pipeline, or repository upkeep changes (e.g., `chore(deps): bump dependencies`).

### Guidelines
*   Keep the summary header under 50 characters.
*   Use the imperative mood (e.g., "Add feature" instead of "Added feature").
*   Reference issue trackers or pull requests in the commit footer when applicable.

---

## 2. Branch Hygiene & Management

Branch isolation prevents code collisions and keeps main branches release-ready.

### Branch Names
Use lowercase strings with directories for naming developer branches:
*   `feature/<description>`: New pipelines, configurations, or enhancements.
*   `bugfix/<description>`: Correcting issues found during builds or test executions.
*   `hotfix/<description>`: Critical production repairs.
*   `release/<version>`: Staging branch for release tagging tests.

### Lifespans
*   Developer branches should remain short-lived (usually less than a week) to reduce merge conflict complexities.
*   Once a branch is merged into `dev` or `main`, **delete** it both locally and on the remote host (GitHub) to prevent repository bloat.

---

## 3. History Cleanliness

*   **Rebasing**: Before merging developer branches, rebase them against the latest target branch updates (`dev`) to align changes cleanly.
*   **Squashing**: Squash minor or intermediate commits (like "fix typo", "test fix") into a single, clean semantic commit before merging to preserve a high-quality development timeline.

---

## 4. Secrets Management & Security

Leaking private credentials (API keys, passwords, security tokens) is a high-risk security violation.

### Prevention
*   Ensure all temporary system folders, packages, and local credential configurations are declared inside the [`.gitignore`](../.gitignore) file.
*   **Never** hardcode plain text secrets or passwords inside files (especially scripts or `Jenkinsfile`). Use environment variables or security credentials stores (like Jenkins Credentials Manager or GitHub Secrets).
*   Run local pre-commit scanning tools (such as GitGuardian, Trufflehog, or `gitleaks`) to detect accidentally added secrets before committing.

### Recovery
If a credential is accidentally committed:
1.  Rotate/invalidate the secret immediately.
2.  Use tools like `git-filter-repo` or BFG Repo-Cleaner to completely erase the object from the repository history. (A standard commit deletion does not remove the secret from old history nodes!).

---

## 5. Pull Request Protocols

*   **Size**: Keep pull requests small and focused (e.g., under 300 lines of changes) to speed up code reviews.
*   **Description**: Outline the goal of the PR, how the changes were tested, and link to associated workspace issues.
*   **Reviews**: Require at least one peer approval before merging code into production-ready branches.
