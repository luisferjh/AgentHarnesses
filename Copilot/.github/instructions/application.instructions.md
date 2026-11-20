---
name: Application layer conventions
description: Conventions for use cases, application services, commands, queries, and ports.
applyTo: "src/Application/**/*.cs"
---

# Application layer

- Organize code around use cases or cohesive application capabilities.
- Coordinate workflows here; keep domain invariants and business rules in the Domain layer.
- Depend on abstractions for persistence, messaging, time, identity, and other external capabilities.
- Do not reference the Api or Infrastructure projects.
- Keep transaction boundaries explicit and aligned with use-case consistency needs.
- Pass `CancellationToken` through asynchronous operations.
- Return application-level results; avoid coupling use cases to HTTP types or transport-specific status codes.
- Keep orchestration readable and avoid service classes that become unrelated collections of methods.
