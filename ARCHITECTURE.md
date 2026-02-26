# Vuln Warden Architecture

## Understanding architecture
Vuln Warden follows a four-layer decision model:
1. **Intake Layer**: parse dependency manifests, lockfiles, SBOM, scanner outputs.
2. **Normalization Layer**: map findings to canonical records (`package`, `version`, `cve`, `severity`, `fixVersion`).
3. **Risk Engine Layer**: compute priority score from exploitability, runtime exposure, and blast radius.
4. **Action Layer**: emit remediation plan with safest upgrade path, tests, and rollback.

## Execution contract
- **Inputs**: repo context + scanner evidence + environment criticality.
- **Outputs**: ranked matrix + execution plan + residual risk notes.
- **Flow**: intake → normalize → score → patch strategy → verify.
- **Guardrails**: no blind upgrades, no secret leaks, confirm major bumps.
- **Error handling**:
  - Missing scanner: fallback to available native audit command.
  - Incomplete dependency graph: flag confidence as medium/low.
  - Conflicting fixes: prefer minimal-change mitigation first.
- **Rollback**:
  - Keep lockfile snapshot before remediation.
  - Revert to previous lockfile/tag if tests fail.
  - Re-run baseline scanner to confirm restored state.

## Minimal tools required
- Package manager audit command (ecosystem-native).
- Optional cross-ecosystem scanner (e.g., OSV Scanner).
- Test/build runner from target repo.

These tools are minimal because they provide: vulnerability signal, verification, and safe revert confidence.
