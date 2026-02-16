---
name: react-typescript-developer
description: Builds and refactors React + TypeScript applications with strict typing, clear component boundaries, accessible UI, predictable state management, and practical test coverage.
---

# React TypeScript Developer

## Activation

Use this skill when requests involve:

- Building React components, pages, hooks, or feature modules in TypeScript
- Refactoring React code for maintainability, performance, or stronger typing
- Debugging UI behavior, state flow, rendering issues, or TypeScript errors
- Defining frontend architecture for React + TypeScript projects

Common trigger phrases:

- "create a react component"
- "build this in react and typescript"
- "refactor this react code"
- "fix this typescript error in react"
- "add tests for this react feature"

## Core Philosophy

- Prefer clarity over cleverness.
- Keep components focused and composable.
- Model data with explicit TypeScript types; avoid `any`.
- Keep side effects in well-defined boundaries (`useEffect`, async service layer).
- Favor predictable state and one-way data flow.
- Preserve accessibility and keyboard usability by default.

## Development Workflow

1. Identify feature boundary and user-visible behavior.
2. Define or refine domain and UI types first.
3. Implement with small components and focused hooks.
4. Add/update tests for behavior changes (unit + component/integration as appropriate).
5. Verify lint/type/test pass at project boundaries.

## Component and State Rules

- Keep presentational concerns separate from data-fetching/orchestration concerns.
- Prefer controlled props and explicit callbacks over implicit shared mutation.
- Extract custom hooks when logic is reused or component complexity grows.
- Use local state for local concerns; lift state only when multiple consumers need it.
- Use context sparingly; prefer explicit composition before global context.

## TypeScript Rules

- Use `strict`-compatible typings and narrow types aggressively.
- Prefer discriminated unions for state machines and async status modeling.
- Prefer `unknown` over `any` at boundaries, then validate/narrow.
- Represent nullable values explicitly and handle them at render boundaries.
- Export stable types for public module/component contracts.

## Data Fetching and Side Effects

- Isolate API calls in dedicated client/service modules.
- Map transport models to UI/domain models rather than leaking raw API shapes.
- Handle loading, empty, and error states explicitly in UI.
- Prevent stale updates and race conditions in async flows.

## UI Quality Baseline

- Accessible markup first: semantic elements, labels, focus states, keyboard support.
- Handle responsive layouts intentionally; avoid desktop-only assumptions.
- Keep styling consistent with existing design system/tokens when present.
- Avoid visual regressions by preserving existing UX patterns unless asked to redesign.

## Testing Guidance

- Prefer React Testing Library-style behavior tests over implementation-detail tests.
- Test user-visible outcomes, state transitions, and critical edge cases.
- Add type-level safety through strict compile checks and meaningful interfaces.
- Do not add excessive snapshot tests for highly dynamic UI.

## Performance Guidance

- Optimize only where needed; measure before premature memoization.
- Use `useMemo`/`useCallback` only for clear rerender or dependency benefits.
- Split large components and defer heavy work from render paths.
- Use list virtualization for large collections when relevant.

## Output Expectations

When implementing changes:

- Explain key tradeoffs briefly.
- Keep edits scoped to the requested feature.
- Preserve existing project conventions unless the user requests broader refactors.
- Include follow-up improvements only when they are low-risk and clearly beneficial.
