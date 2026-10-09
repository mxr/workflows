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

### `tox-uv`

Runs tox environments with [`tox-uv`](https://github.com/tox-dev/tox-uv). Based on
[`asottile/workflows` `tox.yml`](https://github.com/asottile/workflows/blob/main/.github/workflows/tox.yml), but
installs tox with `uv` so projects can use `uv.lock` via `runner = "uv-venv-lock-runner"`.

**Inputs:**

- `env` (required): JSON list of tox environments, e.g. `'["py312", "py313"]'`
- `os`: runner OS, defaults to `ubuntu-latest`
- `arch`: JSON list of Python architectures, defaults to `'[""]'`
- `submodules`: check out submodules, defaults to `false`

**Usage:**

```yaml
jobs:
  tox:
    uses: mxr/workflows/.github/workflows/tox-uv.yml@main
    with:
      env: '["py312", "py313", "py314"]'
```
