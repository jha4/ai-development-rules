# AI Development Rules

A reusable, tool-aware engineering playbook for building and maintaining web apps, mobile apps, APIs, SaaS products, and games with AI coding assistants.

## Sources and what we learned

- [Ponytail](https://github.com/DietrichGebert/ponytail): YAGNI and minimalism, but scope the change by tracing all affected callers, tests, fixtures, configuration, exports, and user data. Do not confuse "small" with "incomplete".
- [Ralph](https://github.com/snarktank/ralph): small user stories with acceptance criteria, an iterative build/check loop, and durable progress/learnings (including progress files and codebase instructions).
- [GSD Core](https://github.com/open-gsd/gsd-core): Discuss → Plan → Execute → Verify → Ship; explicit decisions, bounded plans, requirement coverage, fresh task context, and goal-backward verification.
- [Everything Claude Code (ECC)](https://github.com/affaan-m/ECC): portable rules and skills, specialist workflows, research-first work, security scanning, memory/continuous learning, and tool-specific integration surfaces.
- [CodeRabbit](https://www.coderabbit.ai/): independent review of diffs for bugs, security, edge cases, regressions, and maintainability.

These projects are references, not dependencies. This repository contains an original synthesis; it does not copy their full implementations, tools, or configurations.

## Start here

1. Read [AGENTS.md](AGENTS.md), the cross-agent baseline.
2. Follow [the development workflow](docs/DEVELOPMENT_WORKFLOW.md).
3. Apply [web and mobile rules](docs/WEB_AND_MOBILE_RULES.md).
4. Apply [security rules](docs/SECURITY.md) and [quality gates](docs/QUALITY_GATES.md).
5. Read [advanced engineering patterns](docs/ADVANCED_ENGINEERING_PATTERNS.md) for requirement traceability, task sizing, context continuity, and verification ladders.
6. Use the relevant workflow skill in `.agents/skills/`.
7. For a substantial feature, start with [the feature brief](templates/feature-prd.md); keep state in [the project memory template](templates/PROJECT_MEMORY.md).
8. For difficult bugs, use [verification-first debugging](templates/VERIFICATION_FIRST_DEBUGGING.md).

## Tool entry points and templates

- **Antigravity / Gemini:** [GEMINI.md](GEMINI.md) is the workspace entry point. Antigravity supports `AGENTS.md`, `GEMINI.md`, `.agents/rules/*.md`, and `.agents/skills/*/SKILL.md` in supported workspace setups. Confirm the current tool's loading behavior.
- **Claude Code:** [CLAUDE.md](CLAUDE.md) points to the canonical rules.
- **Google AI Studio:** [copy-ready Build prompt](templates/GOOGLE_AI_STUDIO_PROMPT.md).
- **ChatGPT:** [Project instruction template](templates/CHATGPT_PROJECT_INSTRUCTIONS.md).
- **GitHub Copilot:** [copilot instructions](.github/copilot-instructions.md).

Each AI tool loads context differently. A file existing in GitHub does not automatically mean every tool reads it. Copy or import the relevant files into the project or paste the template into the tool's supported instructions surface.

## Included workflow skills

- `.agents/skills/debugging/SKILL.md` — evidence-first bug investigation.
- `.agents/skills/feature-implementation/SKILL.md` — planning and implementing features.
- `.agents/skills/code-review/SKILL.md` — independent diff review.
- `.agents/skills/database-changes/SKILL.md` — safe schema/query/migration work.
- `.agents/skills/deployment/SKILL.md` — deploy and verify the live application.

## Core principle

**Understand first. Build the smallest complete solution. Verify it works. Report what was and was not verified.**

## Suggested use in every project

1. Copy the relevant entry point and rules into the application repository.
2. Keep project-specific architecture, commands, decisions, bugs, and next steps in that project's own memory file.
3. Use small tasks with observable acceptance criteria.
4. Test at the level the claim requires; a successful build is not proof of end-to-end behavior.
5. Update rules only from evidence-backed, reusable lessons—not one-off guesses.

## License and attribution

This ruleset is intended for personal and project use. The referenced projects retain their own licenses and ownership. Follow their licenses if using their original files or code.
