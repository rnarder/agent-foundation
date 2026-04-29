# Promotion Policy

## Objetivo
Definir cuándo una práctica deja de ser una buena idea local o experimental y pasa a formar parte del core reusable del `Agent Foundation`.

## Niveles
### 1. Core estable
Prácticas ya probadas, explicables y portables.

### 2. Experimental / incubando
Prácticas prometedoras, pero aún con evidencia insuficiente o dependencias contextuales.

### 3. Local only
Prácticas útiles solo para un agente, usuario o host concreto.

## Checklist de promoción al core
Una práctica debería entrar al core solo si responde “sí” a casi todo esto:
- ¿ya demostró valor en más de un caso real?
- ¿reduce coste, riesgo, ruido o babysitting?
- ¿se puede explicar como regla clara?
- ¿no depende de una persona concreta?
- ¿no depende de un host concreto?
- ¿sigue teniendo sentido aunque cambie el modelo principal?
- ¿es más una mejora de sistema que un workaround local?

## Señales de que algo NO debería entrar al core todavía
- solo funcionó una vez
- depende de una combinación rara de host/herramientas
- resuelve un caso muy específico
- necesita demasiadas excepciones
- aún no se ha probado fuera del agente actual

## Flujo recomendado
1. Surge una práctica nueva
2. Se prueba en contexto real
3. Se documenta como experimental si promete
4. Si se repite y demuestra valor, se promueve al core
5. Si se demuestra local/contextual, se deja fuera del core

## Skillify: niveles de promoción durable
No toda mejora merece una skill completa. Promover bien significa elegir el nivel mínimo que evita repetir el fallo o perder la capacidad.

### 1. Regla durable
Usar cuando basta con cambiar comportamiento futuro.
- ejemplo: regla en `lessons.md`, `AGENTS.md` o doc de operación

### 2. Doc / checklist
Usar cuando la mejora es un procedimiento humano-agente.
- ejemplo: verificación antes de cerrar, panorama antes de arquitectura

### 3. Script determinista
Usar cuando el núcleo es mecánico.
- ejemplo: watcher, parser, preflight, healthcheck

### 4. Skill operativa
Usar cuando hace falta routing claro, instrucciones especializadas o combinación de pasos/herramientas.
- debe tener `SKILL.md`
- debe describir cuándo usarla y cuándo no
- idealmente debe apoyarse en scripts/tests si el core es determinista

### 5. Skill + tests + routing + monitoring
Usar cuando la capacidad es crítica, repetible o propensa a regresiones.
- tests o smoke checks
- docs de routing
- estado/logs si corre en background
- verificación de que realmente se invoca

## Criterio de nivel mínimo
Elegir el nivel más bajo que sea:
- durable
- verificable
- fácil de mantener
- suficientemente explícito para que otro agente lo use sin adivinar

No convertir todo en skill. No dejar capacidades importantes solo en memoria conversacional.

## Regla
El core debe crecer despacio. Es mejor un core pequeño y fiable que uno grande y confuso.
