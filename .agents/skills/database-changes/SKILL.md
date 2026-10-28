---
name: database-changes
description: Design, implement, and verify database schema, query, migration, and data-integrity changes safely.
---

# Database Changes Skill

1. Identify the database engine/version, environment, ORM/query layer, migration system, and affected callers.
2. Read schema and existing migration conventions before writing SQL.
3. Confirm expected data shape, volume, constraints, indexes, transaction needs, permissions, and backward compatibility.
4. For production or shared databases, start with read-only inspection and estimates. Confirm target environment explicitly.
5. Prefer additive expand-and-contract migrations for changes that must coexist with old application versions.
6. Never drop, truncate, overwrite, or bulk-update production data without explicit approval and a recovery plan.
7. Use parameterized queries; validate inputs and enforce access control at the correct boundary.
8. Consider NULLs, duplicates, collations, time zones, decimal precision, concurrency, and query plans.
9. Make migrations repeatable or safely detectable where appropriate; document rollback limitations.
10. Test against representative non-production data and verify both existing and new workflows.
11. Report SQL/schema changes, expected impact, backup/rollback, checks run, and any unverified production assumptions.

Never put real credentials or customer data into prompts, logs, tests, or repository files.
