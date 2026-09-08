# Feature Documentation Template

Create one folder per business capability, for example `features/projects/` or `features/billing/`.

```text
features/<feature>/
├── README.md          # Purpose, owner, dependencies, document map
├── feature.md         # User goal, workflows, rules, failure behavior
├── screens.md         # Routes, UI states, components, responsive behavior
├── data.md            # API use, cache/mutation, validation, error handling
├── permissions.md     # Visible actions, denied states, sensitive data
└── tests.md           # Required component/integration/E2E/accessibility tests
```

Create `analytics.md` only for complex measurement needs. Add other files only when a clear independent concern exists.

Before feature implementation, read the root PRD/design/architecture/rules, the relevant `frontend/` standards, and the owning backend module’s contracts.
