# AI Development Rules

A reusable engineering playbook for building and maintaining web apps, mobile apps, APIs, and SaaS products with AI coding assistants.

These rules combine useful principles from:
- [Ponytail](https://github.com/DietrichGebert/ponytail): minimal solutions, reuse existing code, but never cut safety or tests.
- [Ralph](https://github.com/snarktank/ralph): small independently verifiable tasks, quality checks, and persistent learnings.
- [GSD Core](https://github.com/open-gsd/gsd-core): discuss → plan → execute → verify → ship; durable project state and fresh-context planning.
- [Everything Claude Code (ECC)](https://github.com/affaan-m/ECC): reusable skills/rules, security checks, hooks, review, and continuous improvement.
- [CodeRabbit](https://www.coderabbit.ai/): independent review, change-impact analysis, security and edge-case review.

These projects are references, not dependencies. This repository contains an original, lightweight ruleset; it does not copy their implementations.

## Start here

1. Read [AGENTS.md](AGENTS.md) before changing code.
2. Follow [the development workflow](docs/DEVELOPMENT_WORKFLOW.md).
3. Apply [web and mobile rules](docs/WEB_AND_MOBILE_RULES.md) to product work.
4. Apply [security rules](docs/SECURITY.md) to every project.
5. Use [quality gates](docs/QUALITY_GATES.md) before calling work complete.
6. Copy the relevant instructions into the target project's root or coding-agent configuration.

## Core principle

**Understand first. Build the smallest complete solution. Verify it works. Report what was and was not verified.**

## Compatibility

The root `AGENTS.md` is the cross-agent baseline. `CLAUDE.md` and `.github/copilot-instructions.md` point agents to the same standards. Use the files that your chosen coding tool actually reads; do not assume every tool loads every instruction file.

## License

This ruleset is intended for personal and project use. The referenced projects retain their own licenses and ownership.
