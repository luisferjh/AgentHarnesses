# .NET + GitHub Copilot Harness

Base version-controlled structure for using GitHub Copilot in a .NET repository. It separates repository-wide instructions, path-specific instructions, architecture documentation, and the solution's code layout.

## Contents

- `.github/copilot-instructions.md`: shared repository rules.
- `.github/instructions/`: rules scoped to file paths through `applyTo`.
- `docs/`: architecture, engineering standards, development workflow, and Architecture Decision Records (ADRs).
- `src/`: Clean Architecture-style projects.
- `tests/`: unit, integration, and architecture tests.

## Adaptation notes

1. Rename the projects and namespaces to match the product.
2. Adjust the `applyTo` globs if the source layout changes.
3. Update `docs/architecture.md` and the ADRs when the actual architecture is established or changed.
4. Keep instructions concise, stable, and non-duplicated. Put design rationale in `docs/`, not in every instruction file.
5. User-level Copilot preferences belong outside the repository, in the user's Copilot configuration. This repository contains only shared project guidance.

This scaffold intentionally contains no product requirements, task prompts, or custom agent definitions.
