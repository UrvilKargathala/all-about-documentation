# Delivery Phases

## Release goal

- **Release / milestone:**
- **Outcome to prove:**
- **Target date:**
- **Release owner:**

## Phase plan

| Phase | Goal | Deliverables | Entry criteria | Exit criteria |
|---|---|---|---|---|
| 0. Discovery | Validate problem and scope | PRD, risks, success metrics | Stakeholders identified | Scope approved |
| 1. Foundation | Establish safe delivery base | Repo, environments, architecture, CI | Architecture agreed | App deploys and core checks run |
| 2. MVP | Complete primary user journey | Must-have features | Foundation complete | Acceptance criteria met |
| 3. Validation | Test with real users | Feedback, analytics, fixes | MVP usable | Success measures reviewed |
| 4. Launch | Release safely | Runbook, support plan, release notes | Launch approval | Monitoring healthy |
| 5. Iterate | Improve based on evidence | Prioritized next release | Launch data available | Next milestone agreed |

## Phase-wise code plan

Define the code scope before development. A phase should be independently testable and should not contain unfinished work required by an earlier phase.

### Phase 0 — Discovery (no production code)

- Write the PRD, user flows, data needs, risks, and success measures.
- Create spikes or throwaway prototypes only when they answer a specific uncertainty.
- Do not build polished features or connect production data yet.

### Phase 1 — Foundation

**Build:**

- Application skeleton, routing, configuration, environment-variable validation.
- Shared types, linting/formatting, test setup, CI checks, and deployment pipeline.
- Authentication shell, database schema/migrations, logging, error boundary, and basic health check where relevant.

**Tests:** build/type checks, unit-test setup, a smoke test, and deployment verification.

**Do not build yet:** advanced UI, nonessential integrations, or feature-specific shortcuts.

### Phase 2 — MVP

**Build:**

- The smallest complete primary user journey from `prd.md`.
- Required screens, API endpoints, data reads/writes, authorization rules, validation, loading/empty/error states.
- Analytics for the primary success event.

**Tests:** unit tests for business rules, integration tests for core API/data flow, and an end-to-end test of the primary journey.

**Do not build yet:** optional roles, power-user controls, broad customization, or secondary workflows.

### Phase 3 — Validation and hardening

**Build:**

- Fixes from user feedback; usability and accessibility improvements.
- Rate limiting, retries/timeouts, monitoring dashboards, audit logs, backup/recovery work as needed.
- Essential integrations and secondary flows only when evidence supports them.

**Tests:** negative-path, permissions, accessibility, performance, and integration-failure tests.

### Phase 4 — Launch

**Build:**

- Production configuration, feature flags, migration/rollback support, support tooling, and release notes.
- Alerts, operational runbook, legal/privacy surfaces, and onboarding/help content.

**Tests:** production smoke test, rollback drill where risk warrants it, and launch checklist sign-off.

### Phase 5 — Iterate

**Build:**

- Only improvements tied to measurable product feedback, technical debt with clear impact, or the next approved milestone.
- Refactors in separately scoped changes; remove obsolete code and dependencies as features evolve.

**Tests:** preserve the full regression suite and add coverage for every fixed production issue.

## Feature-to-phase mapping

| Feature / technical item | Phase | Code areas affected | Tests required | Owner | Status |
|---|---|---|---|---|---|
| App setup and CI | 1 |  | Smoke/build |  | Not started |
| Primary user journey | 2 |  | Unit + integration + E2E |  | Not started |
| Monitoring and resilience | 3 |  | Failure-path/performance |  | Not started |
| Launch controls | 4 |  | Production smoke |  | Not started |

## Current work

| Item | Phase | Owner | Status | Blocker / next step |
|---|---|---|---|---|
|  |  |  | Not started |  |

## Definition of done

- Acceptance criteria met and relevant tests pass.
- Design, accessibility, and error states reviewed.
- Analytics/logging and operational ownership are in place.
- Documentation and release notes are updated.
- Known limitations are explicit and accepted.
