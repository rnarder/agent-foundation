# Incubating Practices

Objetivo: seguir prácticas prometedoras antes de adoptarlas en Bruno o promoverlas al core de `Agent Foundation`.

## Reglas del sistema
- **Máximo 3 prácticas activas** a la vez.
- Toda práctica incubada debe tener:
  - origen
  - hipótesis
  - scope de prueba
  - criterio de promoción
  - criterio de descarte
  - próximo checkpoint
- Si una práctica no se mueve tras varios checkpoints, se descarta o vuelve a intake.
- **Intake ≠ incubación ≠ adopción**.
- Una práctica solo se promueve cuando mejora algo real sin añadir complejidad innecesaria.

## Estados
- `intake` — idea capturada, aún sin prueba
- `incubating` — en prueba controlada
- `adopted-local` — adoptada en Bruno/sistema local
- `promoted-core` — promovida al Agent Foundation
- `discarded` — no aportó suficiente valor

---

## 1) Progressive disclosure for memory
- **Source:** `thedotmack/claude-mem`
- **Status:** `promoted-core`, `adopted-local`
- **Hypothesis:** buscar primero, leer fragmentos mínimos y expandir solo si hace falta reducirá inflación de contexto y mejorará higiene de memoria.
- **Trial scope:** workflow real de Bruno al consultar memoria/contexto previo antes de responder o actuar.
- **Outcome:** adoptado como principio operativo y promovido a `MEMORY_SYSTEM.md`.
- **Why promoted:** alto valor, bajo coste, encaje natural con el sistema actual y sin complejidad adicional.

## 2) Context segmentation for long tasks
- **Source:** `gsd-build/get-shit-done`
- **Status:** `incubating`
- **Hypothesis:** dividir tareas largas en slices/briefs más atómicos reducirá context rot y mejorará claridad/verificación en trabajos complejos.
- **Trial scope:** tareas largas con subagentes, investigación o cambios multi-paso.
- **Promote if:** mejora claridad, reduce mezcla de contextos y hace más limpia la verificación sin meter demasiada ceremonia.
- **Discard if:** se vuelve burocrático, fragmenta demasiado o no mejora la calidad real.
- **Next checkpoint:** próximo trabajo largo con subagentes o ejecución en varias fases.

## 3) Verification loops more explicit
- **Source:** `gsd-build/get-shit-done`, `affaan-m/everything-claude-code`
- **Status:** `incubating`
- **Hypothesis:** checkpoints más explícitos y baratos dentro del flujo mejorarán fiabilidad sin volver pesado el proceso.
- **Trial scope:** cambios de config, routing, modelos y tareas con varias piezas.
- **Promote if:** detecta errores antes, mejora confianza de cierre y sigue siendo ligero.
- **Discard if:** duplica verificación ya existente o mete demasiados pasos sin beneficio claro.
- **Next checkpoint:** próxima modificación relevante de config o flujo operativo.
