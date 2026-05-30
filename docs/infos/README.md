# Capsule Guidelines

`docs/infos/` contains focused, agent-readable capsules. These files are
maintained by AI agents and reviewed through normal Git history.

## Rules

- One capsule should cover one durable topic.
- Keep capsules short enough to read only when relevant.
- Use exact paths, commands, and constraints.
- Record why a convention exists when the reason is not obvious from code.
- Remove stale guidance as soon as source code or workflow changes make it wrong.
- Do not add generic programming advice.
- Keep consumer-visible fork changes in the root `README.md`; capsules may
  explain when to update the README, but should not replace the README change
  log.
- Keep Hugo user documentation in `docs/content/`; `docs/infos/` is for
  development-agent guidance only.

## Suggested Capsule Names

- `build-workflow.md`
- `downstream-consumption.md`
- `fork-readme-maintenance.md`
- `scss-architecture.md`
- `release-policy.md`
- `known-pitfalls.md`

Create these only when they contain useful project-specific facts.
