---
name: code-review
description: Review code changes for correctness, security, regressions, edge cases, maintainability, and test coverage without rewriting unrelated code.
---

# Code Review Skill

Review the actual diff and surrounding call sites, not just the summary.

## Review order
1. Requirement coverage: does the change meet each acceptance criterion?
2. Correctness: boundary conditions, null/empty values, ordering, concurrency, time zones, rounding, retries, idempotency.
3. Security: authentication versus authorization, object ownership, tenant isolation, validation, injection, secret exposure, unsafe file handling.
4. Data integrity: migrations, constraints, transactions, duplicate records, rollback, compatibility with existing data.
5. Reliability: timeouts, dependency failures, cancellation, reconnects, duplicate requests, persistence across restarts/instances.
6. UI/UX: responsive behavior, accessibility, loading/empty/error/success states, disabled controls, real navigation.
7. Performance and maintenance: unnecessary queries/renders/dependencies, duplicated business logic, confusing abstractions.
8. Tests: happy path, negative path, regression, permissions, concurrency where relevant.
9. Deployment: environment variables, runtime versions, routes, start command, health check, migrations, logs.
10. Diff hygiene: unrelated files, generated artifacts, debug output, secrets, undocumented breaking changes.

## Findings format
For each finding, state severity, file/line or exact location, failure scenario, impact, and suggested fix. Prioritize actionable issues; do not report speculative style preferences as bugs. If no issue is found, state review scope and limitations. Do not claim tests were run unless they were run.
