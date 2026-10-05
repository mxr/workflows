# workflows

Reusable GitHub Actions workflows. Also hosts personal cron workflows.

## Workflows

### `pre-commit-typing`

Runs `mypy`, `ty`, or `pyright` type checking via pre-commit. Extracts typing hooks from your `.pre-commit-config.yaml`
and runs them in isolation.

**Requirements:**

- `.pre-commit-config.yaml` must set `default_language_version.python`
- At least one type checking hook from the list above

**Usage:**

```yaml
jobs:
  typing:
    uses: mxr/workflows/.github/workflows/pre-commit-typing.yml@main
```
