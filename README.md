# check-changie-changes-action

This action checks if a new changelog file has been added in the commits. If not, it will fail the workflow.

## Usage

```yaml
name: Check changelog changes
steps:
  - uses: actions/checkout@v3
    with:
      fetch-depth: 0

  - name: Has changes file
    # Some automated tooling might not immediately create a changelog file. These can be handled independently
    if: github.actor != 'dependabot[bot]'
    uses: mach-composer/check-changie-changes-action@v0.1.0
```

