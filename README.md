# Vuln Warden

Dependency vulnerability triage and patch planning skill for local-first repositories.

## What it does
- Builds a fast inventory of dependencies (direct/transitive where available).
- Classifies CVEs by exploitability, runtime exposure, and business impact.
- Produces an ordered remediation plan with rollback-ready steps.
- Enforces guardrails for production-safe updates.

## Included files
- `SKILL.md` — canonical English skill spec.
- `SKILL.es.md` — Spanish skill spec.
- `ARCHITECTURE.md` — understanding/decision architecture.
- `USE_CASES.md` — realistic execution scenarios.
- `LIMITS.md` — non-goals, constraints, and legal/safety limits.

## Quick use
Trigger this skill when you need to triage package vulnerabilities, prioritize patches, or prepare safe dependency update rollouts.

## Version
Initial release: `v0.1.0`.
