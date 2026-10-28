# Advanced Engineering Patterns

This document expands the practical ideas selected from Ponytail, Ralph, GSD Core, Everything Claude Code, and CodeRabbit. The projects are references, not dependencies; this file is an original synthesis, not a copy of their full implementations.

## 1. Research first, but proportionately
- Inspect repository structure, package scripts, dependency versions, current tests, deployment files, and relevant code paths before choosing a solution.
- For external platform behavior, use current official docs and record version-sensitive assumptions.
- Search existing code and project history before adding a new dependency or creating a parallel implementation.
- Stop researching when the available evidence is sufficient to choose a low-risk implementation; do not turn a small fix into an open-ended research project.

## 2. Make requirements traceable
For substantial work, give requirements stable IDs (for example, AUTH-01, ROOM-03, DATA-02). Map each to implementation areas and a verification method. A feature is not complete simply because code exists; its acceptance criteria must be checked.

## 3. Plan for atomic, testable slices
Each task should:
- Have one clear outcome.
- Have explicit files or system areas likely to change.
- Be small enough to understand and verify independently.
- State prerequisites and acceptance criteria.
- Avoid overlapping edits with concurrent work.
- End with a test/check and a short factual summary.

Prefer a thin end-to-end path before building many disconnected screens or modules.

## 4. Protect context and project continuity
- Treat chat history as temporary; record durable decisions and state in the project.
- Use `templates/PROJECT_MEMORY.md` as a handoff format.
- Start each new session by reading the memory, current plan, relevant source files, and recent changes.
- For long tasks, summarize completed work, evidence, decisions, blockers, and next steps before changing context.
- Do not save secrets or raw customer data in memory files.
- Avoid dumping the entire repository into every prompt; provide relevant files and targeted context.

## 5. Use a verification ladder
Choose checks in increasing cost:
1. Static inspection and diff review.
2. Focused unit or component tests.
3. Integration tests for API/database boundaries.
4. Lint, typecheck, and production build.
5. Browser/device smoke test.
6. Staging or production smoke test, only with permission and suitable safety.
7. Multi-client, concurrency, load, or recovery tests for high-risk real-time flows.

Run the smallest check that can disprove the current hypothesis first. Do not report a higher-level verification if only a lower-level check ran.

## 6. Keep implementation and review distinct
- The implementer should explain intended behavior and tests.
- A review pass should independently inspect the diff, acceptance criteria, edge cases, security, and downstream effects.
- Review findings must be actionable and tied to a concrete failure scenario.
- An AI review is useful but does not replace automated tests, runtime evidence, or human approval for high-impact changes.

## 7. Learn from failures safely
After a meaningful bug or release:
- Record the confirmed root cause, evidence, fix, regression test, and remaining uncertainty.
- Convert recurring lessons into concise reusable rules or skills.
- Do not turn a one-off guess into a global rule.
- Keep rules small and specific; archive stale guidance.

## 8. Cost-aware architecture
- Prefer a simple modular architecture until real requirements justify more services.
- Evaluate free-tier quotas, sleep/cold starts, storage persistence, bandwidth, function duration, database limits, API charges, and vendor lock-in.
- A service advertised as free may still require billing setup or incur charges if configured incorrectly.
- Keep credentials server-side and test production-like configuration before launch.

## 9. Definition of done
A task is done when:
- Acceptance criteria are met or exceptions are explicit.
- Relevant tests and checks have actual results.
- The diff has been reviewed.
- Security and data impacts have been considered.
- Docs and project memory are updated when needed.
- Deployment is verified if deployment was part of the task.
- The final report distinguishes facts, unverified items, and remaining risks.
