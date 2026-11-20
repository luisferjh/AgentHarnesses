# Repository instructions

## Scope
These instructions apply to the entire repository. More specific files under `.github/instructions/` add rules for matching paths.

## General engineering principles
- Follow the architecture and conventions documented in `docs/`.
- Prefer simple, explicit, maintainable solutions over unnecessary abstractions.
- Preserve existing public contracts unless a change is explicitly part of the work being performed.
- Keep changes focused; avoid unrelated refactoring and formatting churn.
- Do not introduce a new package, framework, or architectural pattern without a clear technical reason.
- Reuse established project abstractions where they are appropriate; do not create generic abstractions for one-off use.
- Keep business rules independent from infrastructure and delivery mechanisms.

## .NET and C#
- Use the repository's configured target framework and language version; do not upgrade them implicitly.
- Follow nullable reference type settings and address nullability warnings intentionally.
- Use asynchronous APIs for I/O-bound work and propagate `CancellationToken` where the surrounding API supports it.
- Avoid `.Result`, `.Wait()`, and `async void` outside event-handler scenarios.
- Dispose owned disposable resources; prefer `using` / `await using` and dependency injection-managed lifetimes.
- Use dependency injection through the existing composition root.
- Keep configuration externalized; do not hard-code secrets, credentials, or environment-specific values.
- Use structured logging and avoid logging secrets or sensitive data.

## Quality and verification
- Add or update automated tests for behavior changes.
- Keep unit tests deterministic and independent of external services.
- Use integration tests for persistence, transport, and external-system boundaries.
- Run the relevant build and test commands after changes; report what was and was not run.
- Do not claim a build or test passed unless its result was observed.

## Security
- Treat external input as untrusted and validate it at system boundaries.
- Enforce authorization at the appropriate application boundary; do not rely only on UI visibility.
- Use parameterized data access and established encoding mechanisms.
- Never commit secrets, tokens, private keys, or production data.
- Prefer least-privilege access and secure defaults.

## Documentation
- Update relevant documentation when architecture, setup, operational behavior, or public contracts change.
- Record significant architectural choices in `docs/decisions/` using the ADR format.
