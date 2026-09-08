# Components and Design-System Use

## Component contract

| Component | Owner | Purpose | Inputs/events | Variants | Accessibility notes | Tests |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## Rules

- Prefer semantic HTML before custom behavior.
- Document default, hover, focus, disabled, loading, error, and success states where applicable.
- A component becomes shared only after genuine reuse or when it is a foundational primitive.
- Shared components must not fetch feature data or encode feature permissions.
- Use design tokens rather than one-off color, spacing, typography, or breakpoint values.
- Define keyboard behavior, accessible name, focus behavior, and responsive behavior for interactive components.
