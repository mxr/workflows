# GitHub release workflow

This reusable workflow creates a GitHub release for the current tag.

## Requirements

- The workflow must run on a tag ref.
- The caller repository must allow `contents: write` for its Actions `GITHUB_TOKEN`.

## Example

```yaml
jobs:
  release:
    uses: mxr/workflows/.github/workflows/github-release.yml@XXX # vYYY
```
