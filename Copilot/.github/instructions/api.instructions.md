---
name: API layer conventions
description: Conventions for HTTP endpoints, controllers, middleware, filters, and API contracts.
applyTo: "src/Api/**/*.cs"
---

# API layer

- Keep HTTP concerns in this project: routing, model binding, transport-level validation, status codes, and serialization.
- Keep business decisions in the Application or Domain layers; do not implement business workflows in controllers or endpoint delegates.
- Map application outcomes to HTTP responses consistently with existing API conventions.
- Use request and response contracts rather than exposing persistence entities.
- Apply authentication and authorization explicitly to protected endpoints.
- Validate untrusted request data at the boundary and return safe, consistent error responses.
- Propagate `CancellationToken` to application calls and I/O operations.
- Do not expose exception details, stack traces, secrets, or internal implementation data to clients.
- Keep API versioning, OpenAPI metadata, and compatibility conventions consistent with the existing service.
