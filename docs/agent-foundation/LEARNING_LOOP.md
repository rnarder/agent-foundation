# Learning Loop

## Objetivo
Capturar aprendizajes, errores, correcciones y capacidades faltantes sin inflar memoria ni convertir cada observación en regla permanente.

## Tesis
Un agente mejora más cuando tiene una bandeja cruda de aprendizaje y una política clara de promoción.

No todo aprendizaje merece memoria larga. No todo error merece una skill. Pero nada importante debe quedarse solo en chat.

## Inbox crudo recomendado
Usar un directorio ligero tipo `.learnings/` en el workspace del agente:

- `.learnings/LEARNINGS.md` — correcciones, insights, knowledge gaps, best practices, patrones recurrentes
- `.learnings/ERRORS.md` — fallos de comandos, APIs, integraciones o automatizaciones
- `.learnings/FEATURE_REQUESTS.md` — capacidades pedidas o detectadas como recurrentes

Este inbox es una zona de triage, no la fuente de verdad permanente.

## Flujo
1. **Capturar**
   - registrar resumen corto, fecha, área, prioridad y acción sugerida
   - redactar/sanitizar; no volcar transcripts ni logs largos

2. **Clasificar**
   - correction
   - error
   - feature_request
   - best_practice
   - pattern
   - knowledge_gap

3. **Promover o descartar**
   - comportamiento durable → `memory/lessons.md` o equivalente
   - incidente serio → `memory/MEMORY_ERRORS.md` o postmortem equivalente
   - contexto estable → memoria curada
   - capacidad reusable → skill/doc/script/test/routing
   - gotcha de herramienta/host → documentación operativa local
   - idea que no aporta → cerrar o borrar cuando sea seguro

4. **Verificar**
   - si la promoción toca código, skill, config o automatización, correr el gate mínimo útil

## Política de coste
No hacer reflexión LLM constante por rutina.

Preferir:
- captura determinista
- revisión humana/agente solo cuando hay material real
- promoción durante incidentes, heartbeats útiles, cierre de tareas o revisiones periódicas de bajo coste

Evitar:
- loops de auto-reflexión frecuentes
- resúmenes diarios vacíos
- usar LLM para clasificar cosas obvias
- llenar memoria larga con logs crudos

## Criterio de promoción
Promover si cumple una o más:
- se repitió
- evitó o evitaría un fallo costoso
- el usuario lo corrigió explícitamente
- afecta seguridad, privacidad, dinero o acciones externas
- mejora una capacidad reusable
- reduce coste o ruido operativo

No promover si:
- fue anécdota de una sola vez
- ya existe una regla suficiente
- añade más complejidad que prevención
- no tiene acción clara

## Relación con skillify
`learning-loop` es la entrada; `skillify` es una posible salida.

- learning-loop decide qué merece sobrevivir
- skillify convierte una solución importante en capacidad durable

## Seguridad e higiene
- No guardar secretos, tokens, claves, env vars ni datos privados innecesarios.
- Redactar outputs y comandos sensibles.
- Mantener entradas cortas y accionables.
- Revisar/promover en lotes pequeños para evitar cementerios de TODOs.
