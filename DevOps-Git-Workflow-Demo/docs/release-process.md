# Release Process

This section explains versioning and release planning for the repository.

## Semantic Versioning

Semantic Versioning (SemVer) uses three parts: `MAJOR.MINOR.PATCH`.

- `MAJOR` — incompatible API or workflow changes.
- `MINOR` — new features or enhancements that remain backward compatible.
- `PATCH` — bug fixes and small improvements.

## Version Examples

| Version | Description |
|---|---|
| `v1.0.0` | Initial Release |
| `v1.1.0` | Added features or documentation updates |
| `v2.0.0` | Major update with breaking changes |

## Release Workflow

1. Create a release branch from `dev`.
2. Update documentation and release notes.
3. Test the release branch.
4. Merge the release branch into `main`.
5. Tag the merge commit.
6. Push `main` and tags.

## Example Release Tagging

```bash
git checkout main
git pull origin main
git merge --no-ff release/v1.0
git tag -a v1.0.0 -m "Initial Release"
git push origin main
git push origin v1.0.0
```

## Release Notes Example

```markdown
## [1.0.0] - 2026-07-03
### Added
- Initial project structure
- Setup and branching documentation
- Git workflow and command reference
```

## Tagging Best Practices

- Use annotated tags for releases.
- Keep tag messages short and descriptive.
- Push tags explicitly when releasing.
