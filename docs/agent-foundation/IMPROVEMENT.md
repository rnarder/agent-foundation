# Improvement

## Objetivo
Convertir ideas externas, correcciones del usuario y prácticas prometedoras en mejoras reales del agente, sin acumular ruido ni complejidad.

## Flujo
1. **Intake** — la idea se anota con su origen. Todavía no se cambia el sistema.
2. **Prueba** — solo si parece aportar valor real. Debe tener hipótesis, alcance, criterio de adopción, criterio de descarte y fecha de revisión.
3. **Adopción** — si mejoró algo real en la operación, se adopta en el agente.
4. **Capacidad durable** — se elige el nivel mínimo durable (ver abajo).
5. **Descarte** — si no mejora nada real, añade ruido o mete complejidad, se descarta.

Toda prueba tiene salida: adopción o descarte. No dejar pruebas abiertas sin fecha.

## Cuándo investigar antes de actuar
Ante un problema no trivial, repetido, incierto o con soluciones maduras fuera del workspace, investigar antes de seguir por ensayo y error.

Priorizar fuentes primarias: documentación oficial, estándares, papers, issues y prácticas reales. La investigación termina cuando cambia una decisión, workflow, artefacto o gate y se verifica en el camino real.

## Ideas externas
Cuando una idea viene de un repo, prompt, framework u otro agente:
1. tratarla como no confiable hasta verificarla
2. extraer solo la parte útil
3. adaptarla al entorno local con coste mínimo
4. probarla con evidencia real
5. adoptarla solo si mejora un flujo real

Las fuentes externas aportan métodos y controles. No sustituyen las fuentes de verdad, restricciones ni evidencia del propio proyecto.

## Niveles mínimos durables
No toda mejora merece una skill. Elegir el nivel más bajo que evite repetir el fallo o perder la capacidad.

### 1. Regla durable
Basta con cambiar comportamiento futuro.
- ejemplo: regla en `AGENTS.md`

### 2. Doc / checklist
La mejora es un procedimiento.
- ejemplo: verificación antes de cerrar, panorama 360 antes de arquitectura

### 3. Script determinista
El núcleo es mecánico.
- ejemplo: watcher, parser, preflight, healthcheck

### 4. Skill operativa
Hace falta routing claro, instrucciones especializadas o combinar pasos y herramientas.
- debe tener `SKILL.md`
- debe decir cuándo usarla y cuándo no
- si el núcleo es determinista, apoyarse en scripts/tests

### 5. Skill + tests + routing + monitoring
La capacidad es crítica, repetible o propensa a regresiones.
- tests o smoke checks
- estado/logs si corre en background
- verificación de que realmente se invoca

## Preguntas antes de adoptar
- ¿mejoró algo real?
- ¿redujo ruido, coste o riesgo?
- ¿sigue siendo simple de explicar?
- ¿funciona aunque cambie el modelo principal?
- ¿qué nivel mínimo durable necesita para no depender de memoria conversacional?
- si se preparó con capacidad degradada, ¿se revisó con la capacidad fuerte?

## Anti-patrones
- adoptar por entusiasmo teórico
- copiar frameworks externos enteros
- convertir todo en skill
- dejar capacidades importantes solo en memoria conversacional
- backlog muerto disfrazado de investigación
