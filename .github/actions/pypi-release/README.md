# PyPI release action

This composite action builds a release, publishes the distributions to PyPI with trusted publishing, and creates a GitHub release for the current tag.

## Requirements

- The caller job must run `actions/checkout` before this action.
- The caller job must set `environment.name` to `pypi` and configure the matching PyPI trusted publisher.
- The caller job must grant `id-token: write` and `contents: write` permissions.

## Example

```yaml
jobs:
  release:
    runs-on: ubuntu-latest
    environment:
      name: pypi
      url: https://pypi.org/p/<your-pypi-project-name>
    permissions:
      contents: write
      id-token: write
    steps:
    - uses: actions/checkout@de0fac2e4500dabe0009e67214ff5f5447ce83dd # v6.0.2
      with:
        persist-credentials: false
    - uses: mxr/workflows/.github/actions/pypi-release@main
```

Pin the action reference to a commit SHA or release tag in real usage.
