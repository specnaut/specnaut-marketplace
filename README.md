# specflow-marketplace

Curated marketplace catalog for the [Specflow](https://github.com/mkrlabs/specflow) plugin.

Specflow is a spec-driven workflow with backlog, planning, review, and audit phases. This repository hosts the canonical `.claude-plugin/marketplace.json` catalog that powers two install paths from a single source of truth.

## Install for Claude Code

```text
/plugin marketplace add mkrlabs/specflow-marketplace
/plugin install specflow@specflow-marketplace
```

## Install for Copilot CLI

```text
copilot plugin marketplace add mkrlabs/specflow-marketplace
copilot plugin install specflow@specflow-marketplace
```

## What gets installed

The Specflow plugin ships:

- A unified `/specflow` router skill with 19 phases (specify · clarify · plan · tasks · analyze · implement · review · merge · constitution · checklist · groom · tag-version · release-version · list-skills · audit-{security,performance,accessibility,architecture,dependencies}).
- 15 sub-agents (code-reviewer, developer, devops-sre, product-owner, qa-tester, review-coordinator, security-auditor, specflow-expert, test-reviewer, workflow-manager, ui-ux-designer, performance-auditor, a11y-auditor, architecture-auditor, dependency-auditor).
- 7 cross-cutting skills (writing-plans, requesting-code-review, using-specflow, subagent-driven-development, executing-plans, verification-before-completion, brainstorming).
- A `/specflow-auto` chain skill and a `/specflow-review` alias.

See the [Specflow README](https://github.com/mkrlabs/specflow#readme) for the full feature matrix and the [docs site](https://specflow.makerlabs.dev) for narrative documentation.

## Versioning

The `version` field in `.claude-plugin/marketplace.json` is auto-bumped by Specflow's release pipeline (`scripts/sync-to-marketplace.sh`, dispatched from `mkrlabs/specflow`'s `.github/workflows/release.yml`) on every `v*` tag push. PRs land here as `chore: bump specflow to <NEXT>` from the `mkrlabs-bot` identity.

## Reporting issues

File bugs and feature requests on the source repository: <https://github.com/mkrlabs/specflow/issues>. This marketplace repo is catalog-only — do not open product issues here.

## License

The catalog metadata in this repository is published under [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). The Specflow plugin itself is MIT-licensed; see [LICENSE](https://github.com/mkrlabs/specflow/blob/main/LICENSE) on the source repository.
