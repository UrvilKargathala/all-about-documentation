# Frontend Architecture

## Purpose

Define how the frontend is organized. Default to a feature-oriented architecture with explicit shared layers.

```text
app-or-routes/     Route entry points, layouts, page composition
features/          User-facing business capabilities
components/        Shared generic UI components
design-system/     Tokens, primitives, reusable visual patterns
lib/               API client, utilities, framework configuration
hooks/             Reusable UI behavior
state/             Shared client state only
tests/             Cross-feature and end-to-end tests
```

## Ownership rules

- A feature owns its screens, feature-specific components, local state, data adapter, and tests.
- Shared components must remain generic; they do not import feature business logic.
- Routes compose features and define route boundaries; they do not hold complex business logic.
- Durable product data belongs to the backend. Client state is local unless multiple independent areas require it.

## Feature structure

```text
features/<feature>/
├── README.md
├── feature.md
├── screens.md
├── data.md
├── permissions.md
└── tests.md
```

Use this document with `architecture.md`, `rules.md`, and the relevant feature documents before frontend work starts.
