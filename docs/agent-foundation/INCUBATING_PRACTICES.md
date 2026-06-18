# Incubating Practices

Objetivo: seguir prácticas prometedoras antes de adoptarlas localmente o promoverlas al core de `Agent Foundation`.

## Reglas del sistema
- **Máximo 3 prácticas activas** a la vez.
- Toda práctica incubada debe tener:
  - owner
  - origen
  - hipótesis
  - scope de prueba
  - criterio de promoción
  - criterio de descarte
  - próximo checkpoint
- Si una práctica no se mueve tras varios checkpoints, se descarta o vuelve a intake.
- El agente mantenedor de Foundation es responsable de revisar las incubaciones en el checkpoint o, como máximo, en 30 días si el checkpoint era condicional y no ocurrió.
- **Intake ≠ incubación ≠ adopción**.
- Una práctica solo se promueve cuando mejora algo real sin añadir complejidad innecesaria.

## Estados
- `intake` — idea capturada, aún sin prueba
- `incubating` — en prueba controlada
- `adopted-local` — adoptada en un agente/sistema local
- `promoted-core` — promovida al Agent Foundation
- `discarded` — no aportó suficiente valor

---

## 1) Progressive disclosure for memory
- **Source:** `thedotmack/claude-mem`
- **Status:** `promoted-core`, `adopted-local`
- **Hypothesis:** buscar primero, leer fragmentos mínimos y expandir solo si hace falta reducirá inflación de contexto y mejorará higiene de memoria.
- **Trial scope:** workflow real de un agente al consultar memoria/contexto previo antes de responder o actuar.
- **Outcome:** adoptado como principio operativo y promovido a `MEMORY_SYSTEM.md`.
- **Why promoted:** alto valor, bajo coste, encaje natural con el sistema actual y sin complejidad adicional.

## 2) Context segmentation for long tasks
- **Source:** `gsd-build/get-shit-done`
- **Owner:** Bruno
- **Status:** `adopted-local`
- **Hypothesis:** dividir tareas largas en slices/briefs más atómicos reducirá context rot y mejorará claridad/verificación en trabajos complejos.
- **Trial scope:** tareas largas con subagentes, investigación o cambios multi-paso.
- **Promote if:** mejora claridad, reduce mezcla de contextos y hace más limpia la verificación sin meter demasiada ceremonia.
- **Discard if:** se vuelve burocrático, fragmenta demasiado o no mejora la calidad real.
- **Checkpoint review 2026-06-18:** adoptado localmente en el agente de referencia como criterio operativo para trabajos largos, subagentes y revisiones por fases. No promover como doctrina core nueva por separado todavía: el valor está en aplicarlo con ligereza dentro de flujos de planificación, subagentes y continuidad ligera, no en añadir más estructura.
- **Next decision:** mantener local; reconsiderar promoción core solo si otro agente necesita el patrón explícito.

## 3) Verification loops more explicit
- **Source:** `gsd-build/get-shit-done`, `affaan-m/everything-claude-code`
- **Owner:** Bruno
- **Status:** `promoted-core`, `adopted-local`
- **Hypothesis:** checkpoints más explícitos y baratos dentro del flujo mejorarán fiabilidad sin volver pesado el proceso.
- **Trial scope:** cambios de config, routing, modelos y tareas con varias piezas.
- **Promote if:** detecta errores antes, mejora confianza de cierre y sigue siendo ligero.
- **Discard if:** duplica verificación ya existente o mete demasiados pasos sin beneficio claro.
- **Checkpoint review 2026-06-18:** promovido. Hubo evidencia repetida de valor en cambios de configuración, routing/modelos, flujos operativos, actualizaciones y auditorías post-fallback. El patrón ya vive en `VERIFICATION.md` y en reglas de post-config/post-update.
- **Next decision:** no necesita seguir incubando; mantener como regla core ligera.

## 4) PRD to vertical executable issues
- **Source:** AI Hero article `5 Agent Skills I Use Every Day` (`to-prd` / `to-issues` pattern), adapted locally in Bruno as `prd-vertical-issues`.
- **Owner:** Bruno
- **Status:** `adopted-local`, `incubating` for core promotion
- **Hypothesis:** after panorama/PRD/planning, converting the agreed direction into vertical slices with acceptance criteria, dependencies and verification will reduce context burn and make subagent/human execution cleaner.
- **Trial scope:** next large website, automation or multi-agent implementation where a plan needs to become executable work.
- **Promote if:** it produces clearer handoffs, better parallelization, and fewer vague/horizontal tasks without adding heavy ceremony.
- **Discard if:** it duplicates existing planning guidance or creates issue-writing overhead without improving execution.
- **Checkpoint review 2026-06-18:** no hay evidencia suficiente para promover al core porque no se ha usado aún en un proyecto grande real con descomposición vertical. La adopción local sigue siendo válida como skill del agente de referencia, pero la promoción Foundation queda pendiente.
- **Next checkpoint:** próximo plan sustancial de web/automatización que requiera descomposición en tareas ejecutables; si no ocurre antes de 2026-07-18, revisar y decidir `promoted-core`, `adopted-local-only` o `discarded`.
