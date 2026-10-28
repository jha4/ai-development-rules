# Web, Mobile, and SaaS Rules

## Product and MVP
- Build for a clearly identified user and primary job-to-be-done.
- Keep the first release small. Prioritize the complete critical journey over a large set of shallow features.
- Turn feature requests into concrete acceptance criteria and empty/error/loading states.
- Use real user flows rather than decorative screens with fake data, unless the app is explicitly a prototype.
- Make assumptions visible and confirm choices that materially affect cost, data ownership, privacy, or architecture.

## Architecture
- Choose the simplest architecture that meets actual scale and platform needs.
- Prefer a modular monolith over microservices for a small MVP unless a concrete requirement justifies separation.
- Keep components focused; do not create an abstraction for a single trivial use without a reason.
- Define contracts between frontend, backend, and database.
- Do not duplicate business rules across clients when they affect authorization, money, game state, or data integrity.
- Use environment-specific configuration and keep secrets on the server.

## Frontend
- Use semantic components and established design tokens/patterns already in the project.
- Ensure responsive layouts for common mobile and desktop sizes.
- Use accessible form labels, keyboard behavior, visible focus, sufficient contrast, and helpful error messages.
- Avoid layout shifts and unnecessary client-side state duplication.
- Model async UI explicitly: idle, loading, success, empty, and error as applicable.
- Prevent double submissions and communicate when a save/action has completed.
- Confirm destructive actions and offer recovery/undo when appropriate.

## Backend and APIs
- Validate input at the trust boundary and enforce authorization for every operation.
- Use structured errors and stable API response contracts.
- Add rate limits and abuse controls for public endpoints when appropriate.
- Design retries and idempotency for payments, webhooks, room creation, uploads, and other non-repeatable actions.
- Set sensible timeouts and handle dependency failure.
- Avoid leaking stack traces, secrets, internal identifiers, or personal data to clients.

## Database and multi-tenancy
- Define ownership and tenant boundaries explicitly in the data model.
- Enforce tenant isolation in server-side queries and mutations, not just UI filters.
- Add foreign keys, uniqueness constraints, and indexes where they protect integrity or real query patterns.
- Use versioned migrations and backup/recovery plans for important data.
- Avoid destructive resets in any environment containing user data.
- Document retention, export, and deletion behavior where user data is stored.

## Authentication and permissions
- Prefer mature authentication providers or framework primitives over home-grown password/session systems.
- Authorization must be checked server-side on each protected resource.
- Use least privilege and deny access by default.
- Test unauthenticated, unauthorized, expired-session, and cross-tenant scenarios.
- Do not expose service-role or admin keys to browser/mobile bundles.

## Real-time features and games
- Decide which side owns the canonical state; for competitive or shared games, the server should validate important state transitions.
- Do not depend on in-memory room state if restarts, multiple instances, or serverless execution are possible.
- Handle reconnects, disconnected players, expired rooms, duplicate messages, stale clients, and invalid moves.
- Test with multiple independent browser/device sessions, not only one client.
- Do not claim multiplayer works based only on a successful page load.

## Mobile applications
- Verify safe-area insets, small screens, orientation changes, touch target size, keyboard overlap, and app lifecycle/resume behavior.
- Support poor or interrupted network conditions where relevant.
- Keep permissions minimal and request them only when the feature needs them.
- Handle loading, offline, empty, and error states.
- Check app signing, build variants, versioning, privacy disclosures, and store requirements before release.
- Test on a real device or emulator when available; state if only a browser preview was checked.

## Hosting and cost
- Respect explicit zero-cost or free-tier requirements.
- Distinguish free tier from free forever; document sleep, quotas, bandwidth, build limits, storage, and database constraints.
- Confirm that the hosting platform supports the app's runtime, WebSockets/SSE, long-lived processes, background jobs, and persistent storage as required.
- Do not treat a successful static frontend deployment as proof that backend APIs or real-time flows work.
- Before production deployment, verify environment variables, domains, routing, health checks, logs, and smoke tests.
