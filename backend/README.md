# Backend Documentation Structure

The backend counterpart uses focused documents instead of one large guide:

```text
backend/
├── backend.md          # Modular-monolith style, layers, module boundaries
├── api.md              # Route conventions, contracts, versioning, idempotency
├── database.md         # Database conventions and ownership rules
├── errors.md           # Global error categories and responses
├── testing.md          # Unit, integration, contract, permissions, failure testing
├── jobs.md             # Queues, retries, idempotency, dead-letter handling
└── observability.md    # Logging, metrics, tracing, alerts
```

Every business backend module should have matching module, routes, data, permissions, and tests documentation under `modules/<module>/`.
