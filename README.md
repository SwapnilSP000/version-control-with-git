# Version Control & Local CI/CD with Git & Jenkins

[![Git Best Practices](https://img.shields.io/badge/workflow-Git%20Best%20Practices-3b82f6?style=flat-square)](https://git-scm.com/)
[![Jenkins CI/CD](https://img.shields.io/badge/ci--cd-Jenkins%20Pipeline-f0883e?style=flat-square)](https://www.jenkins.io/)
[![License: MIT](https://img.shields.io/badge/license-MIT-10b981?style=flat-square)](file:///d:/Devops/EL/EL-version-control-with-git/LICENSE)

## Project Overview

This repository is a practical DevOps portfolio project designed to showcase industry-standard version control workflows, collaborative software development practices, and local CI/CD automation. It serves as a mock environment mimicking a professional team development environment, highlighting how developers integrate code, manage branches, resolve conflicts, and run automated pipelines before code reaches production.

### DevOps Concepts Demonstrated

*   **Semantic Versioning & Release Management**: Organizing release stages and tags for structured releases.
*   **Trunk-Based / Feature Branching Strategies**: Balancing parallel feature updates with shared codebases.
*   **Conflict Resolution & Merging**: Safely resolving integration friction during git pull/merge processes.
*   **Continuous Integration Basics**: Executing a multi-stage software delivery pipeline triggered by branch activity.

---

## Tech Stack

*   **Git**: Local version control tool for tracking and managing source history.
*   **GitHub**: Central collaboration platform for managing branches, Pull Requests (PRs), and releases.
*   **Jenkins**: Open-source automation server utilized for local CI/CD pipeline simulation.
*   **Markdown**: Standard markup language used to document repository specifications and execution details.
*   **VS Code**: Local Integrated Development Environment (IDE) used for code editing and version control integration.

---

## Git Workflow

This project defines a structured development flow to maintain stability in the primary code branch while allowing rapid execution of feature branches. 

```text
  Feature Branch
        |
        v
  Development Branch (dev)
        |
        v
  Pull Request (PR Review)
        |
        v
  Main Branch (main)
        |
        v
  Jenkins Pipeline
```

### Branching Guidelines

*   `main` — Production-ready code and release tags. Direct commits are restricted.
*   `dev` — Active integration branch where features are combined and tested.
*   `feature/*` — Individual branches created from `dev` for specific features or documentation updates.
*   `release/*` — Short-lived branches created from `dev` for final regression testing, documentation updates, and version preparation.
*   `hotfix/*` — Urgent bugfix branches created directly from `main` to address immediate production failures.

---

## Jenkins Integration

This repository contains a declarative pipeline script (`Jenkinsfile`) designed to simulate a basic software release lifecycle.

### Configuration Details

*   **Jenkins Server**: Runs locally on [http://localhost:8080](http://localhost:8080).
*   **Pipeline Definition**: Written in declarative DSL syntax to execute automated build-and-test stages on every push/merge.
*   **Pipeline Stages**:
    1.  **Checkout**: Pulls the code from the Git repository (e.g., `main` or `dev`).
    2.  **Build**: Simulates compiling assets or packaging application dependencies.
    3.  **Test**: Runs unit tests and validates standard configurations.
    4.  **Deploy**: Deploys the packaged code locally or into a simulated staging environment.

---

## Project Structure

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

## Learning Outcomes

By setting up and collaborating in this workspace, developers gain hands-on experience in the following foundational DevOps skills:

1.  **Git Branching & Repository Hygiene**: Creating branch hierarchies (`main`, `dev`, `feature/*`), formulating commit messages matching standards, and maintaining clean branch histories.
2.  **Resolving Merge Conflicts**: Identifying conflicting changes, resolving them inside conflict markers safely, and continuing rebase/merge processes.
3.  **GitHub Collaboration & Code Review**: Operating GitHub Pull Requests, assigning reviewers, documenting changes, and performing standard squash-and-merge or merge operations.
4.  **Semantic Version Tagging**: Generating annotated git release tags (e.g. `v1.0.0`) and compiling changelogs to track project versions.
5.  **CI/CD Pipeline Basics**: Authoring declarative pipeline workflows, orchestrating step stages, and executing jobs triggered by version control actions.

---
*Developed as part of a DevOps Internship portfolio project.*
