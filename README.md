# workflows

Reusable GitHub Actions workflows. Also hosts personal cron workflows.

## Workflows

### `pre-commit-typing`

Runs `mypy`, `ty`, or `pyright` type checking via pre-commit. Extracts typing hooks from your `.pre-commit-config.yaml`
and runs them in isolation.

**Requirements:**

- `.pre-commit-config.yaml` must set `default_language_version.python`
- At least one type checking hook from the list above

**Inputs:**

- `uv-version` (optional): `uv` version, latest if unset, e.g. `0.13.9`
- `pre-commit-version` (optional): `pre-commit` version, latest if unset, e.g. `4.7.0`
- `pre-commit-uv-version` (optional): `pre-commit-uv` version, latest if unset, e.g. `4.4.3`

**Usage:**

```yaml
jobs:
  typing:
    uses: mxr/workflows/.github/workflows/pre-commit-typing.yml@main
    with:
      uv-version: 0.13.9
      pre-commit-version: 4.7.0
      pre-commit-uv-version: 4.4.3
```

### `tox-uv`

Runs tox environments with [`tox-uv`](https://github.com/tox-dev/tox-uv). Its API mirrors
[`asottile/workflows` `tox.yml`](https://github.com/asottile/workflows/blob/main/.github/workflows/tox.yml), but it
installs tox with `uv` so projects can use `uv.lock` via `runner = "uv-venv-lock-runner"`.

**Inputs:**

- `env` (required): JSON list of tox environments, e.g. `'["py312", "py313"]'`
- `os` (required): runner OS, e.g. `ubuntu-latest`
- `uv-version` (optional): `uv` version, latest if unset, e.g. `0.13.9`
- `tox-version` (optional): `tox` version, latest if unset, e.g. `4.67.15`
- `tox-uv-version` (optional): `tox-uv` version, latest if unset, e.g. `1.37.9`

**Usage:**

```yaml
jobs:
  tox:
    uses: mxr/workflows/.github/workflows/tox-uv.yml@main
    with:
      env: '["py312", "py313", "py314"]'
      os: ubuntu-latest
      uv-version: 0.13.9
      tox-version: 4.67.15
      tox-uv-version: 1.37.9
```
