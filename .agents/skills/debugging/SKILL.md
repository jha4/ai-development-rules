---
name: debugging
description: Evidence-first investigation and repair for bugs in existing applications, including frontend/API/database/deployment and multiplayer failures.
---

# Debugging Skill

1. Read root `AGENTS.md`, project memory, and relevant architecture/deployment docs.
2. Restate expected versus actual behavior and collect exact safe error evidence.
3. Inspect the relevant code and trace the full path from UI through API/server to persistence and back.
4. Reproduce before editing when possible. If not possible, say so and identify the missing evidence.
5. Build a ranked hypothesis list; for each hypothesis, identify evidence and the cheapest distinguishing test.
6. Inspect logs, network status, environment configuration, dependency/runtime versions, and deployment state as appropriate. Never expose secrets.
7. Run read-only diagnostics first for databases and production systems. Ask before destructive actions.
8. Fix the confirmed cause with the smallest maintainable change. Do not mask errors or add retries as a substitute for understanding the failure.
9. Add a regression test or repeatable verification scenario.
10. Run relevant checks and test the actual affected flow.
11. Update project memory with root cause, evidence, changes, verification, remaining uncertainty, and next steps.

## Required output
- Confirmed facts
- Hypotheses / unknowns
- Diagnostic steps performed
- Root cause or why it remains unconfirmed
- Files changed
- Checks run and results
- Unverified behavior and next step
