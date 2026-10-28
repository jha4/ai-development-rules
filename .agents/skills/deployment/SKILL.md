---
name: deployment
description: Prepare, deploy, diagnose, and verify web app or API releases on hosting platforms such as Vercel and Render.
---

# Deployment Skill

1. Identify the exact repository, branch/commit, project/service, environment, root directory, framework, runtime, build command, start command, and output directory.
2. Inspect project scripts and current platform configuration before changing settings.
3. Verify required environment variable names and scopes without displaying secret values.
4. Confirm port binding, routes, health/readiness behavior, database connectivity, runtime compatibility, and migration requirements.
5. Estimate cost and free-tier constraints: sleep/cold starts, execution limits, bandwidth, database limits, storage persistence, and external API charges.
6. Review build output and deployment logs. Distinguish a deployment trigger, queued build, successful build, live release, and verified application behavior.
7. After deployment, test the actual public URL and critical flows, inspect runtime logs, and verify data persistence if relevant.
8. For API and multiplayer deployments, check CORS/origins, websocket support, server state persistence, multiple instances, and client-to-server connectivity.
9. Avoid destructive changes, production-impacting configuration changes, or billing changes without explicit approval.
10. If deployment fails, use the debugging skill and record the exact error, evidence, and next diagnostic step.

## Required output
- Target and commit
- Configuration changes
- Build/deploy status with evidence
- Live smoke-test results
- Known limitations/cost risks
- Rollback or next step
