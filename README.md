# flutter-version-number-action

[![Test](https://github.com/blackfoot-makers/flutter-version-number-action/actions/workflows/main.yaml/badge.svg)](https://github.com/blackfoot-makers/flutter-version-number-action/actions/workflows/main.yaml)

📱 Github Action to read out version number of flutter project from pubspec.yaml

## Usage

```yaml
on:
  push:
    branches:
      - main
name: Test
jobs:
  test:
    name: test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - id: read-version
        uses: blackfoot-makers/flutter-version-number-action@main
        with:
          file-path: example/pubspec.yaml
      - uses: nick-invision/assert-action@v1
        with:
          expected: 0.0.1+1
          actual: ${{ steps.read-version.outputs.version-number }}
```
