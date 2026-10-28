# Development Workflow

Use this workflow for new applications, major features, and difficult bugs. Scale it down for simple tasks.

## Phase 1 — Discuss and discover
1. Restate the desired outcome in plain language.
2. Identify platform, users, must-have behavior, constraints, budget, and success criteria.
3. Inspect existing files, scripts, dependencies, tests, and deployment setup before choosing an implementation.
4. Identify unknowns, risky assumptions, external services, data flows, and integration boundaries.
5. For existing code, map the real path from UI to API to persistence and back.

## Phase 2 — Specify and plan
1. Write a short PRD or task brief for work that is larger than a small fix.
2. Separate must-have MVP scope from later ideas.
3. Describe observable acceptance criteria. Avoid vague criteria like "works perfectly".
4. Break the work into small, ordered tasks that can be implemented and tested independently.
5. Record key architecture choices, data model, API contracts, security boundaries, and deployment assumptions.
6. Prefer a walking skeleton: one thin end-to-end path before building every screen or module.
7. Wait for user approval when product decisions, cost, security, or destructive operations require it.

## Phase 3 — Implement
1. Make one focused change at a time.
2. Read existing components and utilities before creating new ones.
3. Implement the simplest maintainable approach that meets acceptance criteria.
4. Keep UI, business logic, persistence, and external integrations appropriately separated for the scale of the app.
5. Handle loading, validation, failures, retries, and duplicate requests where relevant.
6. Add or update tests alongside the implementation, not as an afterthought.
7. Avoid unrelated formatting or refactoring.

## Phase 4 — Verify
1. Run focused tests first, then relevant broader tests.
2. Run typecheck, lint, build, migrations checks, and automated tests when configured.
3. Exercise the actual user journey in browser/device/emulator when tools allow.
4. Test important negative cases: invalid data, no permission, missing records, network errors, retries, and empty states.
5. Inspect logs and API responses for integration/deployment issues.
6. Review the diff and compare it against the acceptance criteria.
7. Fix failures and repeat verification. Do not bypass checks just to get a green build.

## Phase 5 — Ship and learn
1. Summarize the implementation and test evidence.
2. Update docs, changelog, env examples, and agent rules if the change introduces lasting knowledge.
3. Commit or open a PR using a clear, focused message when authorized.
4. Deploy only to the intended environment and confirm the resulting deployment status.
5. Smoke-test the deployed URL/API and the critical user journey.
6. State exactly what is live, what was tested, what remains untested, and any limitations.
7. Capture recurring pitfalls so future work avoids rediscovering them.

## Task sizing
A task should normally fit in one focused implementation-and-verification cycle. Split broad requests such as "build the whole dashboard", "add authentication", or "fix multiplayer" into specific slices with explicit acceptance criteria.

## Bug investigation checklist
- Reproduce the issue and capture the exact error.
- Find the failing request, component, server route, or external dependency.
- Inspect logs and actual runtime configuration.
- Identify root cause with evidence; label unconfirmed possibilities as hypotheses.
- Fix the root cause, not just the displayed error message.
- Add a regression test.
- Verify locally and/or in the deployed environment.
