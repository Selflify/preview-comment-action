# Selflify Preview Comment Action

Create or update the final pull request comment with preview deployment results.

## Required permissions

The workflow needs:

- `actions: read`
- `issues: write` or `pull-requests: write`

## Usage

```yaml
- uses: Selflify/preview-comment-action@v1
  with:
    github-token: ${{ secrets.GITHUB_TOKEN }}
    pr-number: ${{ needs.prepare.outputs.pr_number }}
    path-name: ${{ needs.prepare.outputs.path_name }}
    preview-base-domain: ${{ secrets.PREVIEW_BASE_DOMAIN }}
    metadata-dir: preview-metadata
```

## Marketplace-style repository layout

- `action.yml` is the public entrypoint for GitHub Actions
- `README.md` is the Marketplace-facing documentation
- `LICENSE` keeps the repo ready for public publishing
- `v1` is the stable tag consumers should pin to

## Publishing flow

1. push the repo updates
2. create or move the `v1` tag
3. optionally create a GitHub Release
4. publish to GitHub Marketplace from the repository UI when you want a listing
