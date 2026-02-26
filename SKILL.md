---
name: vuln-warden
description: Dependency vulnerability triage and safe patch planning for software repositories. Use when auditing CVEs, prioritizing remediation by exploitability/impact, preparing upgrade plans with rollback, or validating security posture before release.
---

# Purpose
Deliver reproducible vulnerability triage and remediation plans without destabilizing production.

# Scope
- Dependency inventory and vulnerability intake.
- Risk scoring and prioritization.
- Patch planning, staged rollout, and rollback notes.
- Verification checkpoints (build/test/runtime smoke).

# Inputs expected
- Repository path and tech stack.
- Lockfiles/SBOM/scanner outputs (if available).
- Environment criticality (prod/staging/internal).
- Constraints (maintenance window, change freeze, compliance).

# Outputs
- Prioritized vulnerability matrix (critical/high/medium/low).
- Recommended remediation strategy per issue.
- Ordered execution plan with verification and rollback.
- Residual risk statement for deferred items.

# Standard workflow (5 steps)
1. Discover dependencies and available security signals.
2. Normalize findings into a single vulnerability list.
3. Score risk with exploitability + exposure + business impact.
4. Define safest patch path (pin, bump, replace, mitigate).
5. Validate, document rollback, and summarize residual risk.

# Commands
Prefer project-native scanners first. Typical examples:
- `npm audit --json`
- `pnpm audit --json`
- `pip-audit -f json`
- `poetry export` + scanner
- `cargo audit --json`
- `osv-scanner --format json .`

# Guardrails
- Never auto-merge dependency updates without tests/build checks.
- Never expose secrets from lockfiles, CI variables, or private registries.
- Treat major-version upgrades as sensitive changes requiring confirmation.
- For unreachable fixes, document compensating controls and revisit window.

# Installation notes
No mandatory vendor lock-in. Works with native package managers and open scanners.

# Test checklist
- Can reproduce vulnerability list from provided inputs.
- Risk ranking matches exposure and runtime usage.
- Patch plan includes validation and rollback.
- Deferred items include explicit owner and deadline.

# Changelog
- v0.1.0 — Initial public release.
