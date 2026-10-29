# External Patterns Intake

Objetivo: capturar ideas útiles vistas en repos/sistemas externos sin meterlas automáticamente al core. Este documento sirve como zona de intake previa a incubación, promoción o descarte.

## Criterio
Cada hallazgo se evalúa por:
- valor real
- coste/complexidad
- portabilidad
- encaje con Agent Foundation
- si conviene **adoptar**, **incubar**, **descartar** o dejar como **radar**

---

## 1) gsd-build/get-shit-done
Repo: https://github.com/gsd-build/get-shit-done

### Qué aporta
- conciencia explícita de **context rot**
- trabajo por fases
- ejecución por unidades atómicas
- verificación integrada al flujo
- uso de fresh context para tareas largas

### Qué nos interesa
- **segmentación de contexto** para tareas medianas/grandes
- **slices/fases** cuando la tarea realmente lo merece
- **unidades atómicas de ejecución**
- **verification loops** más explícitos

### Qué no compraríamos entero
- permisos agresivos
- workflow pesado para tareas pequeñas
- formalismo excesivo
- marketing/tono como doctrina

### Veredicto
**Adoptar ideas (parcial)**

### Dónde encaja
- `SUBAGENT_POLICY.md`
- `VERIFICATION.md`
- posible futura guía de ejecución por fases

---

## 2) hesreallyhim/awesome-claude-code
Repo: https://github.com/hesreallyhim/awesome-claude-code

### Qué aporta
- mapa del ecosistema
- radar de skills, hooks, plugins y patrones

### Qué nos interesa
- scouting futuro
- descubrimiento de repos concretos cuando necesitemos resolver un problema específico

### Qué no compraríamos entero
- nada doctrinal solo por estar listado ahí
- ninguna práctica al core sin evaluación propia

### Veredicto
**Radar**

### Dónde encaja
- seguimiento de ecosistema
- futuras investigaciones dirigidas

---

## 3) affaan-m/everything-claude-code
Repo: https://github.com/affaan-m/everything-claude-code

### Qué aporta
- idea de **agent harness performance system**
- continuous learning
- verification loops / quality gates
- hooks, skills, routing y seguridad vistos como sistema vivo
- runtime controls / perfiles operativos

### Qué nos interesa
- pensar la **salud del harness** como disciplina
- hacer más explícito el **continuous learning** con gobernanza
- reforzar **quality gates** y verificación recurrente
- estudiar el concepto de **runtime profiles** sin copiar el sistema completo

### Qué no compraríamos entero
- framework total
- complejidad completa del stack
- acoplamiento a su ecosistema concreto

### Veredicto
**Incubar / Adoptar ideas parciales**

### Dónde encaja
- `VERIFICATION.md`
- `PROMOTION_POLICY.md`
- `ROADMAP.md`
- posible scorecard futura de salud operativa

---

## 4) thedotmack/claude-mem
Repo: https://github.com/thedotmack/claude-mem

### Qué aporta
- memoria persistente como sistema
- **progressive disclosure**
- retrieval por capas
- búsqueda antes de expandir detalles
- sensibilidad al coste de tokens/contexto

### Qué nos interesa mucho
- **search first, expand later**
- **layered retrieval**
- memoria como sistema de recuperación, no solo como archivos estáticos
- traer solo el contexto necesario

### Qué no compraríamos entero todavía
- instalación de stack completo sin necesidad concreta
- workers/UI/DB extra por defecto
- complejidad operativa prematura

### Veredicto
**Adoptar ideas (alto valor conceptual)**

### Dónde encaja
- `RECALL.md` (desde v2.0.0)

---

# Síntesis actual

## Adoptar ideas
- `claude-mem` → progressive disclosure, layered retrieval
- `get-shit-done` → segmentación de contexto, atomicidad, verification loops

## Incubar
- `everything-claude-code` → harness health, runtime profiles, continuous learning más explícito

## Radar
- `awesome-claude-code`

---

# Próximos pasos sugeridos
1. Reforzar **context segmentation / slices** en `SUBAGENT_POLICY.md`
2. Endurecer **verification loops** en `VERIFICATION.md`
3. Añadir al `ROADMAP.md`:
   - harness health / scorecard
   - runtime profiles
