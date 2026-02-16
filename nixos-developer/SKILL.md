---
name: nixos-developer
description: Designs, configures, and troubleshoots NixOS systems using reproducible Nix expressions, modular configuration, safe upgrade workflows, and clear rollback strategies.
---

# NixOS Developer

## Activation

Use this skill when requests involve:

- Writing or refactoring legacy NixOS configurations (`configuration.nix`, `hardware-configuration.nix`, module imports)
- Setting up development environments with Nix (`devShell`, package sets, overlays)
- Debugging Nix build, evaluation, activation, or service issues
- Planning system upgrades, migrations, and rollback-safe changes

Common trigger phrases:

- "configure nixos"
- "write a nix module"
- "fix this nix error"
- "set up a dev shell with nix"
- "upgrade nixos safely"

## Core Philosophy

- Reproducibility first: make system state declarative.
- Default to legacy `configuration.nix` workflows unless flakes are explicitly requested.
- Keep modules small, composable, and explicit.
- Prefer stable channels and explicit package/version intent in legacy setups.
- Make changes easy to review and easy to roll back.
- Separate host-specific configuration from shared reusable modules.

## Workflow

1. Clarify target scope (system, user, service, or dev environment).
2. Model desired state declaratively in Nix.
3. Validate legacy config evaluation and imports before switching.
4. Apply changes with rollback-safe `nixos-rebuild` commands.
5. Verify runtime behavior (services, logs, networking, packages).

## Configuration Design Rules

- Use modules to separate concerns (hardware, networking, services, users, desktop/server roles).
- Keep `configuration.nix` readable; move complexity into imported modules.
- Keep defaults in shared modules; override per host cleanly.
- Use typed module options for reusable components.
- Avoid hidden behavior in ad-hoc scripts when Nix modules can express it.
- Keep secrets out of plain Nix files unless explicitly acceptable.

## Legacy-First Package and Channel Guidance

- Assume channel-based or non-flake configuration as the default.
- Prefer stable channels unless there is a clear need for unstable packages.
- Scope package selection explicitly (`environment.systemPackages`, service package options, overlays when needed).
- Use overlays only when default package sets cannot meet requirements cleanly.

## Optional Flakes Path

- Use flakes only when explicitly requested or when migrating from legacy config.
- Keep migration incremental and reversible.
- Avoid mixing broad flake migration with unrelated system changes.

## Package and Environment Guidance

- Prefer packaged dependencies over imperative installs.
- Use `mkShell`/`devShell` for project-local tooling.
- Keep shell environments minimal and task-specific.
- Isolate language ecosystem tooling from global system packages when practical.

## Service and Runtime Debugging

- Validate options and merge behavior before runtime debugging.
- Check activation errors and systemd unit status/logs after switch.
- Confirm firewall, networking, and permissions assumptions explicitly.
- Treat rebuild warnings as actionable until proven harmless.

## Safety and Operations

- Prefer `nixos-rebuild test` before `switch` for risky changes.
- For remote/critical hosts, prefer `nixos-rebuild test` and verify before `switch`.
- Keep rollback path available and verified.
- Batch related changes; avoid mixing many unrelated edits in one rebuild.
- Call out reboot requirements and service restart impact.

## Output Expectations

When implementing changes:

- Show exact files/options being changed.
- Explain tradeoffs briefly (stability vs latest, simplicity vs flexibility).
- Keep steps reproducible and idempotent.
- Include verification commands when behavior is operationally important.
