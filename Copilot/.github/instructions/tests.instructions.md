---
name: Test project conventions
description: Conventions for unit, integration, and architecture tests.
applyTo: "tests/**/*.cs"
---

# Tests

- Name tests so the behavior and expected outcome are clear.
- Follow the test framework and assertion style already used by the repository.
- Prefer the Arrange-Act-Assert structure where it improves readability.
- Test observable behavior and important edge cases rather than private implementation details.
- Keep unit tests fast, isolated, and deterministic; avoid real network or database dependencies.
- Use test doubles only where they clarify a boundary; avoid mocking every collaborator by default.
- Make integration-test dependencies explicit and isolate test data.
- Ensure tests clean up resources and do not depend on execution order.
- Add architecture tests for important dependency-direction rules when the repository uses them.
