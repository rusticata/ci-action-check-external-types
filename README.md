# ci-action-check-external-types

Github CI action to install and run [cargo-check-external-types](https://github.com/awslabs/cargo-check-external-types)

## Inputs

```yaml
inputs:
  rust_version:
    description: |
        Nightly version to use
        See https://github.com/awslabs/cargo-check-external-types/blob/main/rust-toolchain.toml
    default: nightly-2025-08-06
```

## Usage

```yaml
name: CI
on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]
  workflow_dispatch:

jobs:
  readme:
    name: Validate external types appearing in public API
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v5
      - id: cargo-check-external-types
        uses: rusticata/ci-action-check-external-types@v1
```
