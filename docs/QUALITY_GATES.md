# Quality Gates

Use only the gates relevant to the change, but never skip a high-risk gate without stating why.

## Baseline
- [ ] Acceptance criteria are explicit and satisfied.
- [ ] No unrelated files or behavior changed accidentally.
- [ ] No secrets, credentials, private customer data, or debug dumps were added.
- [ ] Error handling is useful and does not expose internal details to end users.
- [ ] Relevant tests were added or updated.
- [ ] Relevant lint, typecheck, and build commands were run.
- [ ] Documentation and environment examples reflect any changed behavior.
- [ ] Diff was reviewed for regressions and incomplete follow-through.

## UI and mobile
- [ ] Main user journey works from start to finish.
- [ ] Loading, empty, error, success, and disabled states are handled.
- [ ] Responsive layout was checked at relevant viewport sizes.
- [ ] Keyboard navigation, focus, labels, contrast, and screen-reader semantics were considered.
- [ ] No fake controls or dead-end navigation remain.
- [ ] Browser/device verification was performed where available.

## API and backend
- [ ] Input validation and authorization occur server-side.
- [ ] Success and failure responses are predictable.
- [ ] Unauthorized, invalid, missing-resource, and dependency-failure cases are tested where relevant.
- [ ] Retry, timeout, duplicate submission, and concurrency behavior is considered.
- [ ] Logs help diagnose issues without leaking secrets or personal data.

## Data and auth
- [ ] Migrations preserve existing data and are repeatable/safely applied.
- [ ] Constraints and indexes fit query patterns.
- [ ] Access checks are enforced for every protected object.
- [ ] Cross-user and cross-tenant access attempts are tested.
- [ ] Password/session/token handling follows the chosen framework's secure defaults.

## Real-time and multiplayer
- [ ] Shared state has a defined source of truth.
- [ ] Reconnect, disconnect, duplicate actions, stale messages, and room expiry are handled.
- [ ] State persistence matches the hosting model.
- [ ] Two or more real clients were tested together when possible.
- [ ] The game cannot advance illegally due to client-only validation.

## Deployment
- [ ] Build and start commands match the platform.
- [ ] Runtime and dependency versions are compatible.
- [ ] Required environment variables are set by name and purpose.
- [ ] Routing, health checks, CORS, and API paths were checked as relevant.
- [ ] Logs and actual deployment status were inspected.
- [ ] Deployed smoke test passed.
- [ ] Free-tier sleep, limits, ephemeral storage, and persistence constraints are documented.

## Independent review
Ask a reviewer or fresh agent to look for:
1. Acceptance criteria not implemented.
2. Bugs outside the edited lines due to changed contracts or assumptions.
3. Security, authorization, tenant-isolation, or privacy gaps.
4. Missing tests and unhandled error paths.
5. Overengineering, duplicate abstractions, unnecessary dependencies, or scope creep.
6. Migrations/deployment steps that can break existing users.

## Honest completion report
Always separate:
- Verified: commands or user journeys actually run and their results.
- Not verified: checks that were not possible or were skipped.
- Risks: known limitations or plausible failure modes still present.
- Deployment: not deployed / deployment started / deployed and smoke-tested.
