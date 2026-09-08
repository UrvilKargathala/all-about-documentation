# Backend Database Standards

## Ownership

Every application table has one owning module. The owner is responsible for its business meaning, validation, migrations, retention/deletion, and relevant tests.

## Rules

- Use a separate database schema only for a clear ownership, security, lifecycle, or organizational reason.
- Do not access another module’s owned tables directly unless the relationship is explicitly documented.
- Define constraints, indexes, relationships, sensitive fields, retention, deletion, and migration impact for material entities.
- Use transactions for multi-record changes that must succeed or fail together.
- Make schema changes reversible where feasible; document rollback/data-backfill plans before deployment.
- Parameterize queries and use least-privileged database access.

See `database/schema-map.md` for source-of-truth ownership and `database/migrations.md` for the change process.
