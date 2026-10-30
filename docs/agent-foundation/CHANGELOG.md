# Changelog

## v3.1.0 — 2026-10-30
Foco: quitar lo que OpenClaw ya hace de serie.

- Retirado `RECALL.md`: el system prompt nativo ya incluye Memory Recall. La regla propia (historia local antes que APIs vivas) pasa a `CORE_PRINCIPLES.md` §10.
- `CORE_PRINCIPLES.md` §9 se reduce a lo que no cubre el preflight nativo de soluciones existentes: investigar hasta aplicar y verificar.
- `IMPROVEMENT.md`, `ERROR_LEARNING.md` y `templates/AGENTS_TEMPLATE.md` sin duplicados del prompt y la plantilla nativos.
- `HOUSEKEEPING.md` acota el watchdog a lo que no ven los updates y la supervisión nativos, y deja claro que los updates del SO no son nativos.
- `SUBAGENT_POLICY.md` remite a las plantillas de roles nativas.
- `README.md` lista lo que el Foundation deliberadamente no cubre.

## v3.0.0 — 2026-10-30
Foco: Foundation general, aplicable justo después del bootstrap nativo y sin contexto de ningún agente concreto.

- Nuevo `START_HERE.md`: adopción justo tras el bootstrap nativo, sin esperar a que el agente "madure". Sustituye a `NEW_AGENT_ADOPTION.md`.
- Nuevo `IMPROVEMENT.md`: de idea o error a mejora durable. Reúne lo general de `ADOPTION_FLOW.md` y `PROMOTION_POLICY.md`.
- Retirados: `ADOPTION_FLOW.md`, `PROMOTION_POLICY.md`, `SOURCE_OF_TRUTH.md`, `EXTERNAL_PATTERNS_INTAKE.md`, `INCUBATING_PRACTICES.md` y `ROADMAP.md`. Eran registros y procesos de mantenimiento del propio Foundation, no doctrina para un agente.
- `CORE_PRINCIPLES.md`, `ERROR_LEARNING.md` y `templates/AGENTS_TEMPLATE.md` alineados.

Versiones anteriores: ver el historial de git.
