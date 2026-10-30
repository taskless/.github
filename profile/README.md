# Taskless

[![Documentation](https://img.shields.io/badge/docs-docs.taskless.io-111111)](https://docs.taskless.io)
[![npm](https://img.shields.io/npm/v/@taskless/cli?label=%40taskless%2Fcli&color=111111)](https://www.npmjs.com/package/@taskless/cli)
[![License: MIT](https://img.shields.io/badge/License-MIT-111111)](https://github.com/taskless/cli/blob/main/LICENSE)
[![Blog](https://img.shields.io/badge/blog-taskless.io%2Fblog-111111)](https://taskless.io/blog)

> Tell AI once. Taskless turns your team's corrections into deterministic rules for AI coding agents. Correct once. Enforced forever.

```bash
npx @taskless/cli
```

---

## What is Taskless?

You describe what you want enforced, and Taskless decides how to check it on every commit, PR, IDE session, and agent run. Each rule compiles to a real check with its own pass/fail fixtures, and no model runs during enforcement. The CLI is open source and works without signing up.

Markdown instructions like `AGENTS.md`, `skills/`, and `.cursor/rules` are injected into prompts and followed inconsistently. Taskless uses analysis instead: a syntax tree for code ([ast-grep](https://ast-grep.github.io)), the text itself for prose ([Vale](https://vale.sh)), your existing linter, or a cross-file runtime check.

## Why Taskless

- **The right check for each convention.** 25+ languages and prose, run locally, handed to your linter's own format when possible.
- **Deterministic.** Rules give the same result on every run. They aren't an AI reviewer's opinion.
- **Fixtures included.** Every rule proves it catches what you intended before it touches your code.
- **One source of truth.** Rules come from team decisions, not scattered markdown files you have to keep in sync.
- **Gets cleaner over time.** Corrections accumulate into rules, so later pull requests need fewer of them.

## Quick start

In a repository with a coding agent configured (a `.claude/`, `.cursor/`, `.opencode/`, or `.agents/` directory), run the installer. It detects your agent tools and installs the Taskless skill into each.

```bash
npx @taskless/cli
```

Ask your agent to help you get started with Taskless. It reviews your codebase and history and helps turn the strongest candidates into rules. Or describe one yourself:

> Create a taskless rule that catches direct fetch() calls without error handling.

Then check your code, locally or in CI:

```bash
./.taskless/bin/cli.mjs check
```

Matches are reported with file, line, severity, and message, and the command exits `1` on error-severity matches.

## Taskless Cloud

For conventions bigger than one team. Free for individual developers and small teams.

- **Provenance.** Every rule traces back to the PR or decision it came from.
- **Governance.** One rule applies across every developer and agent in your org.
- **Authenticity.** Rule code is signed to prevent tampering.
- **GitHub integration.** Tag `@taskless` on a PR or issue to turn a correction into a rule.
- **AI-powered rule generation**, with validation and test cases.

[Set up Taskless Cloud →](https://docs.taskless.io/getting-started/full-setup/)

---

## Links

- Website: [taskless.io](https://taskless.io)
- Documentation: [docs.taskless.io](https://docs.taskless.io)
- Blog: [taskless.io/blog](https://taskless.io/blog)
- Taskless Cloud: [taskless.io/cloud](https://taskless.io/cloud)
- Sign in: [app.taskless.io](https://app.taskless.io)
- npm: [@taskless/cli](https://www.npmjs.com/package/@taskless/cli)
- Contact: [hello@taskless.io](mailto:hello@taskless.io)
