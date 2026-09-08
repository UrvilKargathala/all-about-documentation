# Backend Architecture

## Architectural style

- **Chosen style:** Modular monolith by default.
- **Reason:** Keep one deployable system while enforcing clear business-module ownership.
- **Exception:** Add a separate worker/service only for a documented scale, isolation, or asynchronous-processing need.

## Module boundaries

Each module owns its business behavior, routes, permissions, data lifecycle, jobs, and tests. Modules communicate through documented interfaces; they do not reach into another module’s internal implementation or tables without an explicit documented relationship.

```text
HTTP route / transport
        ↓
Application use case
        ↓
Domain rules
        ↓
Repository / data access
        ↓
Database
```

| Layer | Responsibility | Must not contain |
|---|---|---|
| Route | Parse request, authenticate, validate, map result/error | Business rules or raw queries |
| Application | Coordinate use case, transactions, integrations | HTTP-specific response logic |
| Domain | Invariants, calculations, state transitions | Framework/transport coupling |
| Repository | Queries, persistence mapping, transactions | User-facing decisions |

## Module index

| Module | Capability | Owned routes | Owned tables | Dependencies | Owner |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

## New-module rule

Create a module for a coherent business capability with its own rules, data, permissions, lifecycle, related API operations, jobs, or independent evolution. Do not create one merely for a single table or technical utility.
