# Vuln Warden

[![Language: English](https://img.shields.io/badge/Language-English-blue.svg)](README.md)
[![Idioma: Español](https://img.shields.io/badge/Idioma-Espa%C3%B1ol-green.svg)](README.es.md)

Specialized skill for **security-maintenance** operations in multi-agent environments (OpenClaw/KiloCode).

## Overview

Vuln Warden helps execute security-maintenance tasks with a secure, repeatable, and audit-friendly workflow.

## When to use

- You need structured execution in the **security-maintenance** domain.
- You want reproducible outputs (plan, verification, rollback).
- You need explicit safety guardrails and operator control.

## Core capabilities

- Trigger-based activation for security-maintenance scenarios.
- 4-step workflow (analysis, planning, execution, validation).
- Standardized output format for operations and reporting.
- Security-first guardrails.

## Inputs

- Goal and scope
- Environment/context (repo, VPS, service, etc.)
- Constraints and risk tolerance

## Outputs

- Operational summary
- Applied plan
- Changes made
- Verification evidence
- Rollback steps
- Residual risk

## Files

- `SKILL.md` → English skill spec
- `SKILL.es.md` → Spanish skill spec
- `README.md` → English documentation
- `README.es.md` → Spanish documentation

## Limits and guardrails

- Never expose secrets.
- Never perform destructive actions without explicit confirmation.
- Prefer minimal, reversible changes.

## Troubleshooting

1. Verify tool/auth access.
2. Re-check environment reachability.
3. Reduce to minimal safe scope.
4. Re-run with explicit verification commands.

## Quick example

**Input:** "Audit and improve security-maintenance workflow."

**Expected output:**
- Scope + plan
- Safe execution steps
- Verification commands
- Rollback procedure
