# CI/CD Workflow

This document explains a simple Git and Jenkins workflow for continuous integration and delivery learning.

## Workflow Overview

The goal is to simulate a basic flow using Git and Jenkins.

1. Create a feature branch from `dev`.
2. Push the branch to GitHub.
3. Trigger a Jenkins build.
4. Run a simulated test stage.
5. Merge the feature branch into `dev`.
6. Prepare a release and merge into `main`.

## ASCII Workflow Diagram

```text
Feature Branch
     |
     v
Push to GitHub
     |
     v
Jenkins Build Trigger
     |
     v
Test Stage
     |
     v
Merge to Dev
     |
     v
Release Branch
     |
     v
Merge to Main
```

## Flow Description

- **Git Feature Branch**: Work on a small change in a branch like `feature/ci-demo`.
- **Push to GitHub**: Push the branch so Jenkins can access it.
- **Jenkins Build Trigger**: Start a build manually or via a trigger.
- **Test Stage**: Jenkins runs simulated test commands and reports output.
- **Merge to Dev**: After successful validation, merge the feature branch into `dev`.
- **Release and Main**: Create a release branch if needed, merge into `main`, and tag the release.

## Learning Focus

- Understand how Jenkins can execute pipeline stages against a Git branch.
- Keep the pipeline simple for local CI/CD practice.
- Use Jenkins to reinforce Git branch and merge concepts.
