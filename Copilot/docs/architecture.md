# Architecture overview

> Template: replace the guidance below with the architecture actually implemented in this repository.

## Architectural style

The initial folder layout follows a Clean Architecture-inspired separation. This is a starting point, not a requirement to use every project or layer.

## Projects and responsibilities

| Project | Responsibility | May depend on |
|---|---|---|
| `Api` | HTTP, transport contracts, composition root | Application, Infrastructure (composition only) |
| `Application` | Use cases, orchestration, ports, application contracts | Domain |
| `Domain` | Entities, value objects, invariants, domain events | No other solution project |
| `Infrastructure` | Persistence and external-system adapters | Application, Domain |

Tests should reference the smallest production project surface needed for the behavior under test.

## Dependency direction

The Domain layer is the innermost layer. Application depends on Domain. Infrastructure implements ports defined inward. Api is an entry point and composition root; it wires implementations to abstractions.

```text
Api ───────────────> Application ───────────────> Domain
 │                         ▲                         ▲
 └────> Infrastructure ────┴─────────────────────────┘
```

Avoid dependencies from Domain or Application back to Api or Infrastructure.

## Runtime flow

Document the actual request/event flow here, including validation, authorization, use-case execution, persistence, messaging, and error mapping.

## Cross-cutting concerns

Document the implemented approach for:

- Dependency injection and composition
- Configuration and secrets
- Logging, tracing, and metrics
- Authentication and authorization
- Validation and error handling
- Persistence and transaction boundaries
- Caching and messaging, if present

## Deployment view

Describe hosting, environments, external dependencies, and deployment topology once established.

## Related decisions

See [Architecture Decision Records](decisions/README.md).
