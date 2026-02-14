---
name: java-architect
description: Generates plain Java 21 code using functional patterns, modern concurrency, and minimal side effects. Core logic never throws exceptions. Exceptions are caught at system boundaries only.
---

# Java Architect

name: Java Architect
description: Generates plain Java 21 code using functional patterns, modern concurrency, and minimal side effects. Core logic never throws exceptions. Exceptions are caught at system boundaries only.

## Activation

trigger:
- "create java class"
- "write java code"
- "generate java"
- "implement in java"
- "refactor java"

## Core Philosophy

- Use Java 21 features.
- Prefer records for immutable data.
- Avoid mutable state.
- Avoid null values.
- Avoid try/catch in core logic.
- Core domain logic must never throw exceptions.
- Exceptions are caught and handled only at application boundaries.
- Prefer functional-style patterns.
- Prefer composition over inheritance.
- Separate pure logic from IO.
- No side effects unless explicitly required.

## Architecture Rules

Strict separation of:
- Domain (pure logic)
- Infrastructure (IO, filesystem, network, database)
- Orchestration (wiring)

Domain layer must:
- Be deterministic
- Have no hidden state
- Avoid side effects
- Never throw checked or unchecked exceptions

Boundary layers:
- Catch exceptions
- Translate them into domain-friendly error models
- Return functional error types instead of propagating exceptions

## Error Handling

- Prefer functional error handling patterns.
- Avoid throwing exceptions from core logic.
- Prefer returning:
  - Optional<T>
  - Custom Result<T, E> types
  - Sealed interfaces for error modeling
- Model domain errors explicitly using sealed hierarchies or records.
- If interacting with APIs that throw exceptions:
  - Catch them immediately
  - Convert them into Result or domain error types

## Functional Style Rules

- Use Streams for transformations.
- Use pattern matching (instanceof and switch).
- Prefer small pure functions.
- Avoid shared mutable state.
- Avoid static mutable fields.
- Prefer method references and composition.
- Avoid null checks by design; null should not appear in domain models.

## Concurrency

- Prefer virtual threads when concurrency is required.
- Use structured concurrency where appropriate.
- Avoid shared mutable state in concurrent contexts.
- Favor immutable data across threads.
- Domain logic must remain thread-safe by design.

## Code Organization

- IO at the edges.
- Core logic in pure functions.
- Clear naming and small focused methods.
- Expressive over clever.
- Compositional design.
- Designed for testability by default.
- Plain Java only.

## Testing

- Do not generate tests unless explicitly requested.
