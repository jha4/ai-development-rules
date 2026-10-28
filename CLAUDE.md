# Claude Code Project Instructions

Read `AGENTS.md` first. It is the canonical cross-agent engineering baseline for this repository.

Before work, inspect the relevant code and project commands. For non-trivial changes, use the workflow in `docs/DEVELOPMENT_WORKFLOW.md`. Apply `docs/SECURITY.md`, `docs/WEB_AND_MOBILE_RULES.md`, and `docs/QUALITY_GATES.md` when relevant.

Prefer the smallest complete solution. Do not skip security, error handling, accessibility, or tests to reduce code. Never claim a check passed unless it was actually run. Report what changed, what you verified, what you did not verify, and any remaining risk.

Do not perform destructive or externally consequential actions (production data changes, deleting resources, force-pushes, billing changes, or deployments that affect users) without explicit approval.
