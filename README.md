# Version Control With Git

A structured repository implementing Git version control practices, GitHub collaboration workflows, branching strategies, release management, and Jenkins CI/CD automation.

## Overview

This configuration implements DevOps workflows and Git repository management models. It is designed to demonstrate:

*   **Git Repository Management**: Standard procedures for code versioning, commit hygiene, and history management.
*   **Branch-Based Development Workflow**: Isolation of changes using feature branches to maintain a stable primary codebase.
*   **Pull Request Collaboration**: Code review integration, webhook notifications, and merge conflict resolution.
*   **Version Tagging**: Semantic versioning and release tags for tracking production milestones.
*   **Jenkins Pipeline Integration**: Automation setups to check code quality and build steps locally.

---

## Tech Stack

*   **Git**: Distributing version control and history tracking.
*   **GitHub**: Central collaboration platform for pull request reviews and repository hosting.
*   **Jenkins**: Automation server for continuous integration pipeline runs.
*   **Markdown**: Structural documentation formatting.
*   **VS Code**: Local workspace development environment.

---

## Repository Workflow

The code integration process flows through automated verification gates to ensure main branch health:

```text
Feature Branch
      ↓
Pull Request
      ↓
Development Branch
      ↓
Main Branch
      ↓
Jenkins Pipeline
```

---

## Jenkins Pipeline Screenshots

### Jenkins Dashboard
![Jenkins Dashboard](screenshots/jenkins-dashboard.png)

### Pipeline Execution
![Jenkins Pipeline Success](screenshots/jenkins-pipeline-success.png)

---

## Directory Layout

```text
version-control-with-git/
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── Jenkinsfile
├── LICENSE
├── README.md
├── assets/
│   └── git-workflow-diagram.md
├── docs/
│   ├── branching-strategy.md
│   ├── git-commands.md
│   ├── project-structure.md
│   ├── release-process.md
│   ├── setup.md
│   └── workflow.md
├── examples/
│   ├── cherry-pick-reset-revert.md
│   ├── merge-vs-rebase.md
│   ├── resolving-conflicts.md
│   └── stash-example.md
├── jenkins/
│   ├── ci-cd-workflow.md
│   ├── jenkins-job-setup.md
│   └── jenkins-pipeline.md
└── screenshots/
    ├── README.md
    ├── jenkins-dashboard.png
    └── jenkins-pipeline-success.png
```

---

## Branching Guidelines

This configuration maintains two primary long-lived branches:
*   `main` — Production-ready release code and version tags.
*   `dev` — Active integration branch where features are compiled.

Supporting branches include:
*   `feature/*` — Feature updates branched off `dev`.
*   `release/*` — Release preparation branches branched off `dev`.
*   `hotfix/*` — Urgent production bug fixes branched off `main`.

---

## Git Operations Reference

### Workspace Setup & Cloning

```bash
git clone https://github.com/<username>/version-control-with-git.git
cd version-control-with-git
```

### Feature Branch Development

```bash
git switch dev
git checkout -b feature/<feature-name>
# Develop updates...
git add .
git commit -m "feat: implement workspace changes"
git push origin feature/<feature-name>
```

### Integration & Tagging

1.  Open a Pull Request on GitHub from `feature/<feature-name>` into `dev`.
2.  Once reviewed and merged, prepare the release candidate branch:
    ```bash
    git checkout dev
    git pull origin dev
    git checkout -b release/v1.1.0
    ```
3.  Merge the release branch into `main` and tag the release version:
    ```bash
    git checkout main
    git merge --no-ff release/v1.1.0
    git tag -a v1.1.0 -m "Release implementation version 1.1.0"
    git push origin main --tags
    ```

---

## Technical Outcomes

By implementing this repository setup, the following skills are validated:
1.  **Repository Hygiene**: Formulating semantic branch trees and commit histories.
2.  **Conflict Resolution**: Handling merging issues during branch integration.
3.  **CI/CD Pipeline Automation**: Running local automation setups with declarative Jenkins pipelines to test and verify commits.
