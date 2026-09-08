# Backend Testing Standards

| Test level | Required purpose |
|---|---|
| Unit | Domain rules, calculations, state transitions |
| Integration | Application/database/integration behavior |
| API / contract | Request validation, response shape, error mapping |
| Permission | Authenticated/unauthenticated and resource-level access |
| Job | Trigger, idempotency, retry, failure/dead-letter behavior |
| Failure-path | Dependency, timeout, conflict, and recovery behavior |
| Performance/security | High-risk routes and abuse/security controls |
| End-to-end | Critical journey across client and backend |

Every important operation covers happy path, validation failure, authentication, authorization, not found, conflict where relevant, side effects, and retry/idempotency where relevant.

| Module/operation | Required scenarios | Test level | Owner | Status |
|---|---|---|---|---|
|  |  |  |  |  |
