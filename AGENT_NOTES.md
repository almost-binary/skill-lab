# AGENT_NOTES

## Purpose

`skill-lab` is a curated collection of modular skills for AI agents.

A skill is a focused capability package that teaches an agent how to perform a specific task with clarity and structure. Skills in this repository are intentionally minimal in implementation, but deliberate in design.

This repository is primarily maintained for personal use, but it is public and available for others to explore and adapt.

---

## Design Philosophy

### 1. Skills Should Be Minimal

Skills should:

- Do one thing well.
- Avoid unnecessary verbosity.
- Avoid over-configuration.
- Avoid embedding excessive examples unless required.
- Avoid framework-specific assumptions unless the skill explicitly targets one.

A skill should feel like a clean tool, not a toolbox.

---

### 2. Opinionated but Composable

Skills may express architectural preferences, but they should:

- Remain adaptable.
- Avoid rigid enforcement unless essential.
- Prefer compositional design.
- Encourage clear structure over clever shortcuts.

They guide behavior rather than dictate it.

---

### 3. Clear Boundaries

When a skill generates code or workflows:

- Core logic should be deterministic where possible.
- Side effects should be isolated.
- Exceptions, if relevant, should be handled at system boundaries rather than driving core control flow.
- Error modeling should be explicit rather than implicit.

These are guidelines, not absolute constraints, but they represent the preferred direction.

---

### 4. Modern and Intentional

Skills should favor:

- Modern language and platform features.
- Clean architectural separation.
- Explicit data flow.
- Readable over clever.

Legacy patterns should only appear when explicitly required.

---

## Structure Expectations

Each skill should typically include:

```
skill-name/
  SKILL.md
  templates/      (optional)
  examples/       (optional)
```

`SKILL.md` should clearly define:

- What the skill does.
- When it should activate.
- Its design stance.
- Any notable constraints.

Clarity is preferred over length.

---

## Change Philosophy

This repository is expected to evolve.

When updating a skill:

- Prefer refinement over expansion.
- Avoid silent behavioral shifts.
- Document meaningful philosophy changes in commit messages.
- Keep skills lean even as standards improve.

Discipline should increase over time, not complexity.

---

## Final Note

If a skill feels bloated, ambiguous, or overly prescriptive, it likely needs simplification.

The goal of `skill-lab` is thoughtful capability, not accumulation.

