---
name: Infrastructure layer conventions
description: Conventions for persistence, external integrations, messaging, file storage, and framework adapters.
applyTo: "src/Infrastructure/**/*.cs"
---

# Infrastructure layer

- Implement Application-defined ports and interfaces here; do not move business policy into infrastructure adapters.
- Keep provider-specific code behind focused abstractions.
- Use parameterized queries or the ORM's safe query APIs; avoid constructing SQL from untrusted input.
- Make database transaction and connection lifetimes explicit and consistent with the chosen data-access technology.
- Keep migrations and persistence mappings aligned with the domain and documented persistence strategy.
- Apply timeouts, cancellation, bounded retries, and idempotency where appropriate for remote calls.
- Do not retry non-idempotent operations blindly.
- Keep credentials and environment-specific endpoints in secure configuration providers.
- Avoid leaking provider-specific exceptions or types into the Domain layer.
