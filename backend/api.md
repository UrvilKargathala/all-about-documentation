# Backend API Standards

## Conventions

- Use resource-oriented, lowercase, plural, kebab-case paths: `GET /projects`, `PATCH /projects/:projectId`.
- Use nesting only when ownership is meaningful: `/projects/:projectId/members`.
- Use action endpoints only for genuine domain commands, e.g. `POST /projects/:projectId/archive`; document why it is not normal CRUD.
- Define one API versioning strategy here before production API work begins.
- Use consistent pagination, filtering, sorting, response shape, error shape, and correlation/request ID behavior.

## Route contract

Document every route in its owning module’s `routes.md`.

| Method/path | Purpose | Auth | Permission | Request/validation | Response | Errors | Idempotency/rate limit |
|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |

Each route records its application operation, data effects, side effects, retry behavior, and required tests. The route document is the contract; source code is its executable implementation.
