# Frontend State

Use the narrowest state location that solves the problem.

| State type | Use for | Examples | Documentation needed |
|---|---|---|---|
| Component-local | One component's temporary UI | Modal open, selected tab, draft input | Only if complex |
| URL state | Shareable/navigation state | Filters, page number, view mode | Route contract |
| Server/cache state | Backend-owned data | User profile, project list | Data contract |
| Shared client state | Cross-area session interaction | Theme, unsaved multi-step flow | State owner and lifecycle |

## Rules

- Do not duplicate server data in client state without a documented reason.
- Define initialization, updates, reset behavior, persistence, and sensitive-data limits for shared state.
- Avoid global stores for feature-local state.
- Never persist secrets or sensitive personal data in browser storage unless the privacy/security decision explicitly allows it.
