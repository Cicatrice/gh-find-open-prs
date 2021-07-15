# gh-find-open-prs

This action tries to figure out the open PRs.

## Usage

```yaml
    steps:
      - uses: actions/checkout@v1
      # Find the PR associated with this push, if there is one.
      - uses: Cicatrice/gh-find-open-prs@main
        id: findPr
      # This will echo "Your PR is 7", or be skipped if there is no current PR.
      - run: echo "Your PR is ${PR}"
        if: success() && steps.findPr.outputs.pr[0]
        env:
          PR: ${{ steps.findPr.outputs.pr[0] }}
```
