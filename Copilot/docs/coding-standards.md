# Coding standards

This document records repository-wide engineering conventions. Keep it aligned with `.editorconfig`, analyzers, formatter settings, and CI checks.

## C# conventions

- Follow the configured .NET SDK, target framework, language version, and nullable settings.
- Use consistent naming: PascalCase for types and public members; camelCase for local variables and parameters; follow established conventions for private fields.
- Prefer `var` when the type is obvious from the right-hand side; use explicit types when they improve clarity.
- Keep methods focused and avoid deeply nested control flow.
- Prefer immutable data and explicit state transitions where practical.
- Use records for value-oriented data when their semantics are appropriate, not automatically for every DTO or entity.
- Avoid premature generalization and unnecessary design patterns.

## Async and resource management

- Use `async` / `await` for asynchronous I/O.
- Propagate cancellation through asynchronous call chains.
- Avoid blocking asynchronous code with `.Wait()` or `.Result`.
- Dispose resources according to ownership and lifetime.

## Errors and observability

- Use exceptions for exceptional failures, not routine branching.
- Preserve useful exception context when translating errors.
- Use structured logs with stable property names.
- Never log secrets, credentials, tokens, or unnecessary personal data.

## Dependencies

- Prefer existing platform capabilities and packages already in use.
- Review package maintenance, licensing, security, and transitive dependencies before adding packages.
- Keep dependency versions centrally managed where the repository already uses central package management.

## Formatting and analyzers

- Follow `.editorconfig` and configured analyzers.
- Do not suppress analyzer warnings broadly; use narrow, justified suppressions.
- Avoid unrelated formatting changes.
