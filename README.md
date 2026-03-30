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
