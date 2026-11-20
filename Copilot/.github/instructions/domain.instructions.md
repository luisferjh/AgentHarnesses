---
name: Domain layer conventions
description: Conventions for entities, value objects, domain services, domain events, and business invariants.
applyTo: "src/Domain/**/*.cs"
---

# Domain layer

- Keep the Domain project independent of frameworks, databases, HTTP, messaging providers, and other infrastructure concerns.
- Express business invariants close to the domain state they protect.
- Prefer value objects for concepts defined by their values and entities for concepts with identity and lifecycle.
- Keep constructors and behavior from allowing invalid domain states where practical.
- Use domain services only when behavior does not naturally belong to a single entity or value object.
- Keep domain events focused on meaningful business facts; avoid using them as generic internal notifications.
- Do not add persistence annotations or transport attributes to domain types unless the architecture explicitly requires them.
