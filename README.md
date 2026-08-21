# specnaut-marketplace

Curated marketplace catalog for the [Specnaut](https://github.com/specnaut/specnaut-cli) plugin.

Specnaut is a spec-driven workflow with backlog, planning, review, and audit phases. This repository hosts the canonical `.claude-plugin/marketplace.json` catalog that powers two install paths from a single source of truth.

## Install for Claude Code

```text
/plugin marketplace add specnaut/specnaut-cli-marketplace
/plugin install specnaut@specnaut-marketplace
```

## Install for Copilot CLI

```text
copilot plugin marketplace add specnaut/specnaut-cli-marketplace
copilot plugin install specnaut@specnaut-marketplace
```

## What gets installed

The Specnaut plugin ships:

- A unified `/specnaut` router skill with 19 phases (specify · clarify · plan · tasks · analyze · implement · review · merge · constitution · checklist · groom · tag-version · release-version · list-skills · audit-{security,performance,accessibility,architecture,dependencies}).
- 15 sub-agents (code-reviewer, developer, devops-sre, product-owner, qa-tester, review-coordinator, security-auditor, specnaut-expert, test-reviewer, workflow-manager, ui-ux-designer, performance-auditor, a11y-auditor, architecture-auditor, dependency-auditor).
- 7 cross-cutting skills (writing-plans, requesting-code-review, using-specnaut, subagent-driven-development, executing-plans, verification-before-completion, brainstorming).
- A `/specnaut-auto` chain skill and a `/specnaut-review` alias.

See the [Specnaut README](https://github.com/specnaut/specnaut-cli#readme) for the full feature matrix and the [docs site](https://specnaut.makerlabs.dev) for narrative documentation.

## Versioning

The `version` field in `.claude-plugin/marketplace.json` is auto-bumped by Specnaut's release pipeline (`scripts/sync-to-marketplace.sh`, dispatched from `specnaut/specnaut-cli`'s `.github/workflows/release.yml`) on every `v*` tag push. PRs land here as `chore: bump specnaut to <NEXT>` from the `github-actions[bot]` identity.

## Reporting issues

File bugs and feature requests on the source repository: <https://github.com/specnaut/specnaut-cli/issues>. This marketplace repo is catalog-only — do not open product issues here.

## License

The catalog metadata in this repository is published under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). The Specnaut plugin itself is MIT-licensed; see [LICENSE](https://github.com/specnaut/specnaut-cli/blob/main/LICENSE) on the source repository.
