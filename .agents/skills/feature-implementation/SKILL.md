---
name: feature-implementation
description: Plan and implement a new feature in an existing or new web, mobile, API, SaaS, or game project with testable acceptance criteria.
---

# Feature Implementation Skill

1. Read `AGENTS.md`, project memory, and existing architecture. Inspect relevant files before proposing new ones.
2. Clarify user outcome, platform, users/permissions, constraints, budget, dependencies, and non-goals.
3. For a meaningful feature, create or update a brief using `templates/feature-prd.md`.
4. Write observable acceptance criteria, including invalid input, empty/loading/error states, permissions, and edge cases.
5. Identify the smallest end-to-end path; prefer a working thin slice before broad UI scaffolding.
6. Plan small tasks with file areas, dependencies, and checks. Avoid parallel edits to the same files unless coordination is explicit.
7. Implement one focused slice at a time using existing patterns and dependencies.
8. Validate data at trust boundaries and enforce permissions server-side. Do not put secrets in client bundles.
9. Add/update tests alongside behavior. Include migrations and backward compatibility if data changes.
10. Run relevant tests, lint, typecheck, build, and manual UI/device checks where available.
11. Review the diff for scope creep, fake controls, incomplete flows, and regressions.
12. Update project memory and report verified versus unverified work.

## Required output
Plan, acceptance criteria, changed files, tests/checks, results, risks, and next steps.
