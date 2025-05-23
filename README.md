<!--
SPDX-FileCopyrightText: 2025 Joe Pitt

SPDX-License-Identifier: GPL-3.0-only
-->
# GitHub Action - Get Latest Version from GitHub Package

Get the latest version from a GitHub package.

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| token | The token to authenticate to GitHub with. | Yes |  |
| owner | The owner of the package. | yes |  |
| package_name | The name of the package to query. | Yes |  |
| package_type | The type of package to query (one of: npm, maven, rubygems, docker, nuget, container) | container |
| minimum_version | The minimum version number to accept, e.g. 2.0.0. | No | None |
| maximum_version | The maximum version number to accept, e.g. 2.99.99. | No | None |

## Outputs

| Output | Description | Example |
|--------|-------------|---------|
| tag | The tag for the latest version. | v2.5.3 |
| version | The latest version number. | 2.5.3 |

## Example

```yaml
      - name: Get Latest Matrix Authentication Service Version
        id: version
        uses: joepitt91/action-version-from-github-package@v1
        with:
          token: ${{ secrets.PACKAGE_READER_PAT }}
          owner: element-hq
          repository: matrix-authentication-service
```
