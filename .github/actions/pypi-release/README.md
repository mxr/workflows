# PyPI release workflow

This reusable workflow builds a release, publishes the distributions to PyPI with trusted publishing, and creates a GitHub release for the current tag.

## Requirements

- The caller workflow must be triggered by a tag.
- The caller repository must configure the matching PyPI trusted publisher.

## Example

```yaml
jobs:
  release:
    uses: mxr/workflows/.github/workflows/pypi-release.yml@XXX # vYYY
    with:
      environment: pypi
      project: your-pypi-project-name
```

Both inputs are optional. `environment` defaults to `pypi`, and `project` defaults to the repository name.
