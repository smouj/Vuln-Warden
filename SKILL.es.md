---
name: vuln-warden
description: Triaje de vulnerabilidades de dependencias y planificación segura de parches para repositorios de software. Úsala cuando necesites auditar CVEs, priorizar remediación por explotabilidad/impacto, preparar upgrades con rollback o validar postura de seguridad antes de release.
---

# Propósito
Entregar triaje reproducible y planes de remediación sin desestabilizar producción.

# Alcance
- Inventario de dependencias e ingesta de vulnerabilidades.
- Priorización por riesgo.
- Plan de parcheo con rollout por etapas y rollback.
- Checkpoints de verificación (build/test/smoke runtime).

# Inputs esperados
- Ruta de repositorio y stack tecnológico.
- Lockfiles/SBOM/salidas de escáner (si existen).
- Criticidad del entorno (prod/staging/interno).
- Restricciones (ventana, freeze, compliance).

# Outputs
- Matriz priorizada de vulnerabilidades.
- Estrategia de remediación por issue.
- Plan ordenado con verificación y rollback.
- Riesgo residual documentado para ítems diferidos.

# Flujo estándar (5 pasos)
1. Descubrir dependencias y señales de seguridad disponibles.
2. Normalizar hallazgos en una lista única.
3. Puntuar riesgo por explotabilidad + exposición + impacto.
4. Definir ruta de parcheo más segura (pin, bump, replace, mitigate).
5. Validar, documentar rollback y resumir riesgo residual.

# Comandos
Priorizar escáneres nativos del proyecto. Ejemplos:
- `npm audit --json`
- `pnpm audit --json`
- `pip-audit -f json`
- `cargo audit --json`
- `osv-scanner --format json .`

# Guardrails
- No auto-mergear updates sin tests/build.
- No exponer secretos de lockfiles o registries privados.
- Tratar upgrades major como cambios sensibles.
- Si no hay fix, documentar controles compensatorios y fecha de revisión.

# Notas de instalación
Sin lock-in de proveedor. Compatible con package managers y escáneres abiertos.

# Checklist de prueba
- Lista de vulnerabilidades reproducible.
- Priorización alineada con exposición real.
- Plan incluye verificación y rollback.
- Diferidos con owner y fecha.

# Changelog
- v0.1.0 — Release público inicial.
