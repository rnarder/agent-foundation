# Routing and Isolation

## Objetivo
Formalizar una distinción crítica: organización visible no equivale a aislamiento real.

## Regla maestra
- canales, topics, labels o carpetas = organización y delivery
- sesiones, subagentes, workflows explícitos = aislamiento real

## Qué decide el routing
- dónde entra una tarea
- dónde debe responderse o notificarse
- qué política temática aplicar
- qué rol/agente conviene usar
- qué modelo puede tener sentido por contexto

## Qué decide el aislamiento
- qué contexto conversacional se comparte
- qué memoria o sesión se mantiene separada
- qué herramientas o límites aplican
- qué trabajo conviene ejecutar fuera del hilo principal

## Reglas maduras
### 1. No confundir topic con memoria separada
Un topic puede organizar muy bien la conversación, pero no garantiza separación real.

### 2. El routing debe vivir en archivos
No depender del modelo activo ni de memoria conversacional para reglas de routing relevantes.

### 3. El aislamiento debe ser explícito
Si importa de verdad, usar sesión, subagente o workflow específico.

### 4. Delivery y arquitectura son capas distintas
Que algo se responda en un topic no implica que toda su ejecución deba vivir en ese mismo contexto lógico.

## Patrón reusable
- topic/canal selecciona política inicial
- coordinador decide complejidad y rol
- si hace falta, delega a sesión/subagente
- el resultado vuelve al lugar correcto de delivery

## Continuidad ligera por topic/proyecto
Para agentes que trabajan en grupos, foros o muchos proyectos, puede existir una capa de estado corto por topic/proyecto.

### Objetivo
Evitar perder decisiones, pendientes y reglas locales sin inflar memoria global ni depender de un LLM que “recuerde” todo.

### Forma recomendada
- un archivo corto por topic/proyecto
- decisiones activas
- pendientes reales
- reglas locales
- último checkpoint útil

### Reglas
- no es un log de chat
- no es aislamiento de memoria
- no es fuente de secretos
- no requiere mantenimiento rutinario con LLM
- actualizar solo ante cambios significativos: decisión, cierre, bloqueo, regla durable o checkpoint

### Relación con routing
El topic puede decidir dónde responder y qué estado corto revisar, pero si el trabajo necesita aislamiento real debe usar sesión/subagente/workflow separado.

## Anti-patrones
- asumir que foro/thread = aislamiento
- usar un mismo hilo para trabajos que merecen separación real
- esconder política de routing en prompts efímeros
- mezclar organización social con arquitectura interna
- convertir topic-state en un diario ruidoso
- usar heartbeats/modelos para mantener topic-state sin valor claro
