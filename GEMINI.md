# Antigravity / Gemini Instructions

This file is the Antigravity-compatible entry point for this project. Read `AGENTS.md` first; it is the canonical baseline.

## Before work
- Inspect the existing repository, architecture, scripts, tests, environment configuration, and deployment path before changing code.
- For non-trivial work, follow `docs/DEVELOPMENT_WORKFLOW.md`: Discuss → Plan → Execute → Verify → Ship.
- Use `docs/SECURITY.md`, `docs/WEB_AND_MOBILE_RULES.md`, and `docs/QUALITY_GATES.md` as applicable.
- Load the relevant workflow skill from `.agents/skills/` when the task matches it.

## Execution rules
- Prefer the smallest complete, maintainable solution; do not sacrifice security, accessibility, validation, or tests for brevity.
- Separate facts, hypotheses, and unknowns. Research current external APIs/platform behavior when version-sensitive.
- For multi-step work, state a concise plan, work in small verifiable slices, and preserve project decisions and next steps in the project's memory file.
- Never claim tests, builds, browser checks, or deployments succeeded unless they were actually run and observed.
- Do not expose secrets or run unreviewed scripts, MCP servers, plugins, or hooks with broad permissions.
- Ask before destructive data changes, production-impacting actions, force pushes, billing changes, or irreversible deployments.

## Final report
Summarize changed files and behavior, checks actually run and their results, checks not run, deployment status, and remaining risks.

Antigravity rule/skill documentation: https://antigravity.google/docs/rules/ and https://antigravity.google/docs/commands/learn.
