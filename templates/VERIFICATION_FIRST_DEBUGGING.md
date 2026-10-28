# Verification-First Debugging Brief

Use this before changing code for difficult bugs involving Vercel, Render, APIs, databases, authentication, or real-time multiplayer.

## 1. Bug statement
- Expected behavior:
- Actual behavior:
- Exact error text:
- Reproduction steps:
- First known occurrence:
- Environment: local / preview / production
- URL or route (remove tokens and private query values):
- Affected users / scope:
- Recent changes:

## 2. Evidence to collect
- [ ] Reproduce the issue or clearly state why it cannot be reproduced.
- [ ] Inspect the browser console and network request: URL, method, status, safe request/response body.
- [ ] Trace the request from UI → API/server → database/external service → response.
- [ ] Inspect hosting build logs, runtime logs, health checks, environment variable NAMES, and service status.
- [ ] Compare local, preview, and production configuration.
- [ ] Check the relevant code, package scripts, dependency versions, routes, and deployment settings.
- [ ] For database issues, inspect schema/migrations, constraints, transaction boundaries, permissions, and safe query results.
- [ ] For multiplayer, test two separate clients and inspect room creation, join, state updates, reconnects, expiry, and persistence.
- [ ] Record timestamps and correlation/request IDs where available. Redact secrets and personal data.

## 3. Hypotheses (ranked)
| Hypothesis | Evidence supporting it | Evidence against it | Cheapest test |
|---|---|---|---|
| H1 | | | |

Do not present a hypothesis as the confirmed cause.

## 4. Minimal diagnostic plan
1. Run the cheapest test that distinguishes the leading hypotheses.
2. Gather evidence before editing.
3. Make one focused change that addresses a demonstrated cause.
4. Add a regression test or reproducible check.
5. Run relevant tests, lint/typecheck/build.
6. Verify the actual user journey in the affected environment.
7. Review the diff and record results in project memory.

## 5. Platform-specific checks

### Vercel
- Correct project, root directory, framework preset, build/output settings.
- Build logs and deployment status.
- Environment variables scoped to the correct environment; redeploy after required changes.
- API route/runtime compatibility, function logs, rewrite/redirect behavior.
- Never assume local filesystem or in-memory state persists across invocations.

### Render
- Service type, branch, root directory, build/start commands, runtime port binding.
- Readiness/health behavior, deploy logs, runtime logs, environment variables.
- Confirm the new deployment is live, not merely queued or building.
- Check cold starts, sleep behavior, instance count, disk/persistence, and free-tier limits.

### Database
- Confirm target database/environment before any write.
- Check connection string configuration without exposing credentials.
- Verify schema, migrations, permissions, constraints, transactions, indexes, and query results.
- Use read-only diagnostics first; back up and get approval before destructive changes.

### Multiplayer / real time
- Client must not be the authority for legal game actions or shared room state.
- Verify websocket/HTTP origin, CORS, room ID generation, join code lifecycle, and server logs.
- Check whether storage works across restarts and multiple instances.
- Test two or more separate clients, invalid actions, duplicate requests, disconnect/reconnect, room expiry, and concurrent joins.

## 6. Root cause and fix record
- Confirmed root cause (or say not yet confirmed):
- Evidence:
- Files changed:
- Why the fix addresses the cause:
- Regression test/check:
- Rollback plan if relevant:

## 7. Verification report
- Checks actually run and results:
- Browser/device/deployed checks:
- Checks not run and why:
- Deployment state confirmed from:
- Remaining risks:
- Next step:

Never claim a deployment or fix is successful based only on code changes or a deployment trigger.
