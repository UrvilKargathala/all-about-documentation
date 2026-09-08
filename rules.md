# Project Rules

## 1. What to do

- Start work from a written requirement and acceptance criteria.
- Prefer small, reviewable changes with tests appropriate to the risk.
- Validate external input at every trust boundary.
- Keep credentials in environment variables or a secret manager; never in code or documentation.
- Document meaningful decisions, assumptions, and trade-offs in `memory.md`.
- Make accessibility, privacy, and failure states part of every feature.

## 2. What to avoid

- Do not add a library for a problem the existing stack already solves.
- Do not silently discard data, swallow errors, or expose raw internal errors to users.
- Do not mix unrelated refactors with feature work.
- Do not claim a feature works without verifying its primary path and key failure path.
- Do not collect, retain, or send user data that is not needed for the feature.

## 3. Libraries and dependencies

Before adding one, record: purpose, maintenance status, license, security implications, size/cost, and removal path.

| Dependency | Purpose | Owner | Approval | Review date |
|---|---|---|---|---|
|  |  |  |  |  |

## 4. Error handling

- Return clear, actionable messages to users; use error codes where support needs them.
- Log structured technical context without secrets or unnecessary personal data.
- Categorize errors: validation, authentication/authorization, not found, conflict, dependency failure, unexpected failure.
- Retry only transient operations; use timeouts and idempotency for write operations.
- Alert on sustained failures and document recovery steps for critical workflows.

### Frontend-specific rules

- Never trust client-side validation alone; show accessible inline validation and preserve user input after recoverable errors.
- Handle loading, empty, offline, unauthorized, and retry states deliberately.
- Avoid exposing secrets in browser code, logs, URLs, analytics, or error reports.

### Backend-specific rules

- Authenticate every request and authorize every resource-level action server-side.
- Validate and normalize all request data; use parameterized database queries and safe file handling.
- Set timeouts for network calls; return stable error codes; make retried writes idempotent.
- Protect migrations, destructive operations, and privileged endpoints with explicit review and recovery plans.

## 5. AI boundaries

- AI output is untrusted input: validate, constrain, and log it appropriately.
- Do not let an AI model access secrets, unrestricted tools, or production writes by default.
- Require human confirmation for irreversible, financial, legal, medical, security-sensitive, or external-communication actions.
- State when content is AI-generated and provide correction/appeal paths where relevant.
- Define evaluation cases, safety checks, cost limits, and a fallback when the model is unavailable.

## 6. General working agreements

- Use consistent naming, formatting, and commit conventions.
- Keep the main branch releasable; use code review for production changes.
- Update docs in the same change when behavior or architecture changes.
- Treat user feedback and production incidents as inputs to the next planning cycle.
