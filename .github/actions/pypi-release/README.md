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
      environment_name: pypi
      pypi_project_name: your-pypi-project-name
```

Both inputs are optional. `environment_name` defaults to `pypi`, and `pypi_project_name` defaults to the repository name.
