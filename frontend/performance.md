# Frontend Performance

## Performance budget

| Route / interaction | Target | Measurement | Owner |
|---|---|---|---|
| Initial primary route |  |  |  |
| Main user action |  |  |  |

## Rules

- Document device and network assumptions.
- Split route/component code when it materially improves loading; avoid client-side data waterfalls.
- Define image, font, asset, and third-party script loading strategies.
- Record server-rendered versus client-rendered decisions when relevant.
- Measure key routes with both real-user signals and repeatable lab checks.
- Treat new large dependencies and blocking scripts as architecture decisions with a documented user benefit.
