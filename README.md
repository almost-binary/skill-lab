# skill-lab

A curated collection of modular skills for AI agents.

This repository contains reusable, structured capability packages ("skills") that help AI agents perform specific tasks with clarity and consistency.

Skills in this repository are:

- Focused
- Intentionally minimal
- Architecturally opinionated
- Designed to be composable
- Framework-agnostic unless explicitly stated

---

## What Is a Skill?

A skill is a structured instruction set for an AI agent.

It typically includes:

- A `SKILL.md` file describing behavior and activation triggers
- Optional YAML config in `agents/openai.yaml` for UI/runtime metadata
- Optional templates or examples
- A clear design stance

A skill teaches an agent *how* to approach a problem, not just *what* to generate.

---

## Design Approach

Skills in `skill-lab` generally favor:

- Compositional design
- Clear separation of concerns
- Modern language features
- Explicit error modeling
- Deterministic core logic
- Minimal side effects

They guide behavior rather than dictate it.

---

## Repository Structure

```
skill-name/
  SKILL.md
  agents/
    openai.yaml   (optional)
  templates/      (optional)
  examples/       (optional)
```

Each directory represents a standalone capability that can be used by compatible AI agents.

---

## YAML Configuration

Skills may include YAML config files (typically `agents/openai.yaml`) to define machine-readable metadata.

Common uses:

- `interface.display_name`: user-facing skill title
- `interface.short_description`: concise UI description
- `interface.default_prompt`: suggested invocation prompt
- Optional dependency and policy metadata when needed

Configuration guidelines:

- Keep YAML minimal and explicit
- Quote string values consistently
- Keep behavior-defining logic in `SKILL.md`, not in YAML
- Treat YAML as configuration, not documentation

---

## Who Is This For?

Primarily for personal experimentation and structured AI workflows.

The repository is public and intended for anyone who values:

- Clean, opinionated agent capabilities
- Architectural intent embedded into automation
- Lean and composable skill design

---

## Philosophy

This is a lab, not a dumping ground.

Skills should stay lean.  
Architecture should stay intentional.  
Complexity should be earned.
