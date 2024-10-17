# Setup and Install Action

This is a composite action that sets up PNPM and Node.js, and then installs dependencies.

Steps:
- [pnpm/action-setup@v4](https://github.com/pnpm/action-setup)
- [actions/setup-node@v4](https://github.com/actions/setup-node)
- [pnpm install](https://pnpm.io/cli/install)


## Usage

Here's an example of how to use this action in a workflow file:

```yaml
name: CI

on:
  push:
    branches:
      - main

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: zirkelc/setup-and-install@v1
        with:
          node-version: 20

      - run: pnpm build

      - run: pnpm test
```

## Inputs

| Input         | Description                   | Required | Default |
|---------------|-------------------------------|----------|---------|
| node-version  | Node.js version for setup-node| false    | 20      |
