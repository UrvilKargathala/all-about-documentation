# Architecture

## 1. System overview

State the major parts of the system and how data moves between them.

```text
[User] → [Client / UI] → [API / Backend] → [Database]
                          └→ [External services]
```

## 2. System design

Complete this section before building a feature that changes data, permissions, or external integrations.

### 2.1 Context diagram

Show the system boundary, people using it, and every external dependency.

```text
[End user] ──browser/app──> [Our product]
[Admin/support] ──────────> [Our product]
                                ├──> [Identity provider]
                                ├──> [Primary database]
                                ├──> [File/object storage]
                                ├──> [Email/payment/other integration]
                                └──> [Logs, metrics, error reporting]
```

### 2.2 Container / service diagram

Describe deployable parts, their responsibility, and trust boundaries.

| Component | Responsibility | Communicates with | Owns data? | Scale / availability need |
|---|---|---|---|---|
| Web/mobile client | User interaction and presentation | API, identity provider | No |  |
| API / application service | Business rules and authorization | Database, integrations | No |  |
| Worker / queue consumer | Long-running or retryable work | Queue, database, integrations | No |  |
| Database | Durable product data | API, worker only | Yes |  |
| Object storage | User-uploaded/static files | API, client via signed URL | Yes |  |

### 2.3 Request and data flows

Document the important flows as numbered steps. Include the normal path and what happens when a dependency fails.

| Flow | Trigger | Steps | Data created/changed | Authorization | Failure / retry behavior |
|---|---|---|---|---|---|
| Sign in | User submits credentials | 1. Client → identity provider; 2. token verified; 3. session created | Session | Public → authenticated | Clear error; rate limit; retry permitted |
| Primary action |  |  |  |  |  |
| Async operation |  |  |  |  |  |

### 2.4 API and event contracts

| Interface | Caller → receiver | Contract | Authentication | Versioning / compatibility |
|---|---|---|---|---|
| `POST /resource` | Client → API | Request, response, status/error codes |  |  |
| `resource.created` | API → worker | Event payload and idempotency key |  |  |

Keep request/response schemas close to the code; link them here once defined.

### 2.5 Data model and lifecycle

| Entity | Key fields | Source of truth | Relationships | Sensitive classification | Retention / deletion |
|---|---|---|---|---|---|
| User |  |  |  |  |  |
|  |  |  |  |  |  |

State how data is created, updated, exported, backed up, and deleted. Record migration and rollback plans for schema changes.

### 2.6 Security and trust boundaries

- Identify public entry points, authenticated boundaries, privileged/admin paths, webhooks, and third-party calls.
- Define roles and a permission matrix for every data-changing action.
- Record secret storage, encryption in transit/at rest, audit logging, abuse controls, and incident owner.
- For uploads or AI tools, define content limits, scanning/validation, isolation, and explicit allowed actions.

### 2.7 Reliability and scale plan

| Concern | Target / assumption | Design response | How it is verified |
|---|---|---|---|
| Expected traffic |  |  |  |
| Slow/downstream dependency |  | Timeouts, queue/retry, fallback |  |
| Data loss |  | Backups, restore procedure |  |
| Deployment failure |  | Health checks, rollback |  |
| Security incident |  | Alerting, containment plan |  |

## 3. Technical decisions

| Area | Choice | Why this choice | Alternatives rejected |
|---|---|---|---|
| Frontend |  |  |  |
| Backend |  |  |  |
| Database |  |  |  |
| Authentication |  |  |  |
| Hosting |  |  |  |
| Observability |  |  |  |

## 4. Folder structure

Adapt this to the selected stack; keep business logic separate from UI and infrastructure.

```text
project/
├── apps/                 # Deployable applications (web, API, worker)
├── packages/             # Shared UI, types, utilities, configuration
├── docs/                 # This documentation
├── tests/                # End-to-end and integration tests
├── scripts/              # Repeatable project tasks
├── infra/                # Deployment and infrastructure definitions
├── .env.example          # Required environment-variable names only
└── README.md             # Setup, run, test, deploy
```

## 5. Data and integrations

| System / entity | Owner | Contains sensitive data? | Retention / deletion rule |
|---|---|---|---|
|  |  |  |  |

## 6. Non-functional requirements

- **Security:** authentication, authorization, secrets, input validation.
- **Performance:** response-time and scale expectations.
- **Reliability:** availability target, retries, backups, recovery.
- **Accessibility:** target standard and supported devices/browsers.
- **Privacy:** data collection minimization and consent needs.

## 7. Frontend and backend checklist

| Area | Frontend decisions | Backend decisions |
|---|---|---|
| Application structure | Routes, layouts, components, state ownership | Modules/services, API versioning, background jobs |
| Data | Fetching/caching, loading/empty/error UI, client validation | Data model, migrations, validation, transactions, retention |
| Security | Session handling, protected screens, safe rendering | Authentication, authorization, rate limits, secrets, audit logs |
| API contract | Request/response types, error messages, optimistic updates | Endpoint contract, status/error codes, pagination, idempotency |
| Quality | Component/unit/E2E/accessibility tests | Unit/integration/contract/performance tests |
| Operations | Client error reporting, performance monitoring | Structured logs, metrics, tracing, alerts, backups |

For each row, state the selected approach, owner, and any open decision before implementation.
