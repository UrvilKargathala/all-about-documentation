# Frontend Data and API Use

For each UI data operation, define the contract with the owning backend module.

| Feature | Operation | API contract | Fetch/cache policy | Mutation behavior | UI error/retry | Owner |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## Rules

- Type API requests and responses where the stack allows it.
- Treat the backend as the source of truth for durable product data.
- Define loading, empty, error, and stale-data behavior before coding.
- Document cache invalidation/refetch behavior after every mutation.
- Use optimistic updates only when the rollback experience is safe and clear.
- Client validation improves usability; backend validation is the authority.
- Never expose internal API error details or secrets to users.
