# Backend Error Standards

## Global model

| Category | Meaning | Client response | Retry? | Logging |
|---|---|---|---|---|
| Validation | Invalid input | Field/actionable error | After correction | Safe context |
| Authentication | No/invalid session | Sign-in required | After sign-in | Minimal context |
| Authorization | Action not allowed | Access denied | No | Audit if sensitive |
| Not found | Resource absent/unavailable | Safe not-found response | No | Request context |
| Conflict | Stale or incompatible state | Explain conflict | Usually after refresh | State context |
| Dependency failure | Provider/service unavailable | Temporary failure | Controlled retry | Dependency details |
| Rate limit / timeout | Request constrained or slow | Retry guidance | Controlled retry | Limit/timing |
| Unexpected | Unhandled fault | Safe generic error | Case-by-case | Full secure diagnostics |

## Rules

- Return stable error codes and safe user-facing messages; never expose secrets or internal stack details.
- Modules document domain-specific errors, their global category, retryability, and side effects.
- Log structured context with correlation ID, while minimizing personal/sensitive data.
