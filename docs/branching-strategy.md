# Branching Strategy

This repository uses a branching strategy designed for collaboration and controlled releases.

## Branch Types

| Branch | Purpose |
|---|---|
| `main` | Production-ready code and release tags |
| `dev` | Integration branch for ongoing development |
| `feature/*` | Work on specific improvements or documentation |
| `release/*` | Prepare a new version for release |
| `hotfix/*` | Fix urgent production issues |

## Recommended Branch Workflow

```text
main
  └── dev
        ├── feature/documentation
        ├── feature/git-commands
        ├── feature/workflow-configs
        └── release/v1.0
```

## Branch Descriptions

### main

- Contains stable releases.
- Only merge finished release branches and hotfixes.
- Tag releases from `main`.

### dev

- Active development branch.
- Integrates feature branches.
- Use for the next release candidate.

### feature branches

- Created from `dev`.
- Named with `feature/<short-description>`.
- Keep changes focused and manageable.

### release branches

- Created from `dev` when ready for release.
- Use `release/<version>`.
- Final stage for testing and documentation updates.

### hotfix branches

- Created from `main` for urgent fixes.
- Merge back into both `main` and `dev`.

## Branching Diagrams

<details>
<summary>Branch relationship diagram</summary>

```text
main
│
├─ hotfix/patch
│  └─ merge -> main
│
└─ dev
   ├─ feature/documentation
   ├─ feature/git-commands
   ├─ feature/workflow-configs
   └─ release/v1.0
```

</details>

<details>
<summary>Feature development flow</summary>

```text
dev
└─ feature/<name>
      └─ merge -> dev
```

</details>
