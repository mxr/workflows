# workflows

Reusable GitHub Actions workflows. Also hosts personal cron workflows.

## Workflows

### `github-release`

Creates a GitHub release when a tag is pushed. Uses `gh release create` with
auto-generated release notes.

**Usage:**

```yaml
jobs:
  release:
    uses: mxr/workflows/.github/workflows/github-release.yml@main
```

Or call directly on tag push -- the workflow already triggers on `push: tags: ['*']`.

### `pre-commit-typing`

Runs `mypy` or `ty` type checking via pre-commit. Extracts typing hooks from
your `.pre-commit-config.yaml` and runs them in isolation.

**Requirements:**

- `.pre-commit-config.yaml` must set `default_language_version.python`
- At least one hook with id `mypy` or `ty`

**Usage:**

```yaml
jobs:
  typing:
    uses: mxr/workflows/.github/workflows/pre-commit-typing.yml@main
```
