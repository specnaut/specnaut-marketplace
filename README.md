# specnaut-marketplace

Marketplace catalogs for [Specnaut](https://github.com/specnaut/specnaut-cli), a spec-driven
workflow for coding agents: planning, implementation, review and delivery.

## Install for Claude Code

```text
/plugin marketplace add specnaut/specnaut-marketplace
/plugin install specnaut-plugin@specnaut-marketplace
```

## Install for Copilot CLI

```text
copilot plugin marketplace add specnaut/specnaut-marketplace
copilot plugin install specnaut-plugin@specnaut-marketplace
```

## What gets installed

`specnaut-plugin` serves the same skills and sub-agents the `specnaut` binary scaffolds into a
project, as a user-scope plugin: the `/specnaut` router (plan → tasks → implement → review →
merge, plus the audit phases), `/board`, `/ship`, the review and expert agents, and a
`SessionStart` bootstrap. See the [Specnaut README](https://github.com/specnaut/specnaut-cli#readme)
for the full picture.

## How the catalogs are published

The catalogs are not written here. They live in specnaut-cli under `packaging/marketplace/`,
beside the plugins they list, are validated by that repository's CI, and have every entry pinned
to the release tag by its version bump. `.github/workflows/sync-from-cli.yml` copies them here,
verbatim, from the latest release — hourly, and at once when a release dispatches it.

There are two files because the two installers read different dialects for "a subdirectory of a
GitHub repository":

| File | Read by | Source shape |
| --- | --- | --- |
| `.claude-plugin/marketplace.json` | Claude Code | `git-subdir` with `url` and `path` |
| `.github/plugin/marketplace.json` | Copilot CLI (checked first) | `github` with `repo` and `path` |

Edit the catalogs in specnaut-cli, never here: a change made here is overwritten by the next
release.

## Reporting issues

File bugs and feature requests on the source repository:
<https://github.com/specnaut/specnaut-cli/issues>. This repository is catalog-only.

## License

The catalog metadata in this repository is published under
[CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). Specnaut itself is MIT-licensed; see
[LICENSE](https://github.com/specnaut/specnaut-cli/blob/main/LICENSE) on the source repository.
