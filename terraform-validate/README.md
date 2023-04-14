# terraform-validate GH action

## Description

A GitHub action that installs terraform to run the `validate` action accross the terraform code.

## Usage

```yaml
name: Terraform Validate

on:
  push:
    branches: [main, master]
  pull_request:
    types: [opened, reopened, synchronize]

jobs:
  code-validate:
    name: Validating Terraform
    runs-on: ubuntu-latest
    outputs:
      validate: ${{ steps.validate.outcome }}
    steps:
      - uses: Xat59/terraform-actions/terraform-validate@main
        id: validate
```
