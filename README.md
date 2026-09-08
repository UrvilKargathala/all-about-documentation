# Project Documentation Kit

Use this structure before implementation begins. Keep decisions short, specific, and updated in the same change as the code they govern.

## Documentation hierarchy

```text
Product:     PRD → Design → Phases
System:      Architecture → Rules → Memory
Platform:    Frontend / Backend / Database standards
Feature:     One folder per user-facing business capability
Support:     Design system, integrations, operations
```

## Root documents

| Document | Answers |
|---|---|
| `prd.md` | Why are we building this, for whom, and what must it do? |
| `design.md` | What experience should users receive? |
| `phases.md` | In what phases will we deliver it? |
| `architecture.md` | How does the complete system fit together? |
| `rules.md` | Which engineering, safety, and AI rules always apply? |
| `memory.md` | Which durable decisions and lessons must be retained? |

## Frontend documents

| Document | Primary question |
|---|---|
| `frontend/frontend.md` | How is the frontend codebase organized? |
| `frontend/routing.md` | How do routes, layouts, and navigation work? |
| `frontend/components.md` | How are components shared and maintained? |
| `frontend/data.md` | How does the UI read and change server data? |
| `frontend/state.md` | Where does each kind of client state belong? |
| `frontend/testing.md` | What frontend tests are required? |
| `frontend/accessibility.md` | What accessibility standard is required? |
| `frontend/performance.md` | How do we protect load and interaction performance? |

## Backend and supporting structure

```text
backend/       backend.md, api.md, database.md, errors.md, testing.md, jobs.md, observability.md
database/      schema-map.md, migrations.md, schemas/<schema>.md
features/      <feature>/README.md, feature.md, screens.md, data.md, permissions.md, tests.md
design-system/ foundations.md, components.md, content.md
integrations/  <provider>.md
operations/    deployment.md, migrations.md, backup-recovery.md, incident-response.md
```

## Suggested order before coding

1. Complete `prd.md`, `design.md`, and `phases.md`.
2. Agree on `architecture.md`, including system design and frontend/backend boundaries.
3. Select the relevant frontend and backend standards.
4. Create the feature folder and its UI/API/data/permission/test contracts.
5. Implement, test, and update documentation together.
