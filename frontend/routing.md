# Frontend Routing and Navigation

Document every meaningful route in the table below.

| Path | Owner | Access | Parameters | Layout | Loading/error boundary | Notes |
|---|---|---|---|---|---|---|
|  |  | Public / authenticated / role |  |  |  |  |

## Rules

- Use stable, meaningful URLs; document redirects and renamed routes.
- Define public, authenticated, and role-restricted behavior.
- Put shareable filters, sorting, pagination, and view configuration in URL state where appropriate.
- Do not place secrets, personal information, or large transient data in URLs.
- Specify browser back/forward behavior, deep-link behavior, not-found pages, titles, and metadata.
- Define route-level loading and error boundaries for slow or failed route data.
