# Vuln Warden

## Qué es

**Vuln Warden** es una skill especializada en **security-maintenance** para ecosistemas multiagente (OpenClaw/KiloCode), diseñada para ejecutar tareas con seguridad, trazabilidad y resultados reproducibles.

## Cuándo usarla

- Cuando la tarea pertenece al dominio de **security-maintenance**.
- Cuando necesitas flujo estructurado: análisis → plan → ejecución → validación.
- Cuando necesitas reporte profesional con verificación y rollback.

## Qué hace

- Define triggers claros de activación.
- Ejecuta proceso operativo obligatorio en 4 pasos.
- Aplica reglas de seguridad y guardrails.
- Entrega salida estandarizada para auditoría y operación.

## Inputs esperados

- Objetivo técnico.
- Alcance y restricciones.
- Entorno objetivo (repo, VPS, servicio, etc.).
- Riesgo/tolerancia esperada.

## Outputs esperados

- Plan breve y accionable.
- Cambios realizados (si aplica).
- Verificación reproducible.
- Rollback y riesgo residual.

## Límites y seguridad

- No exponer secretos.
- No ejecutar acciones destructivas sin confirmación explícita.
- Evitar cambios no trazables o no verificables.

## Troubleshooting

1. Verificar credenciales/herramientas disponibles.
2. Validar acceso al entorno objetivo.
3. Reducir alcance a cambio mínimo seguro.
4. Reintentar con evidencia y logs.

## Ejemplo rápido

**Input:** “Necesito revisar y endurecer el flujo de security-maintenance”.

**Output esperado:**
- Diagnóstico inicial
- Plan en pasos
- Implementación incremental
- Validación + rollback

## Archivos de la skill

- `SKILL.md` (EN)
- `SKILL.es.md` (ES)
- `README.md` (este documento)
