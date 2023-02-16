# Shared workflows

This repository contains shared workflows to be used in all repositories withing this organization.

## Using workflows

Official [documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows) gives good examples on how to use reusable workflows. All secrets should be inherited for easier management. 

## Available workflows

### Test and lint

| input name | type   | required | default |
|------------|--------|----------|---------|
|node_version| string | false    | 16      |

Example: 

```
jobs:
  test-and-lint:
    uses: OperationMonkey/shared-workflows/.github/workflows/test_and_lint.yml@main
```

### Publish NPM

| input name | type   | required | default |
|------------|--------|----------|---------|
|node_version| string | false    | 16      |
|workspace   | string | false    |         |

Example:

```
jobs:
  publish_npm:
    uses: OperationMonkey/shared-workflows/.github/workflows/publish_npm.yml@main
    with:
      workspace: packages/tsconfig
    secrets: inherit
```
