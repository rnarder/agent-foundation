# Subagent Policy

## Principio
Delegar solo cuando el beneficio en foco, aislamiento o paralelismo supera el coste de coordinación.

## Patrón recomendado
- Un coordinador habla con la persona.
- Subagentes especializados trabajan por debajo.
- Los topics/canales organizan; las sesiones/subagentes aíslan de verdad.
- El usuario no debería cargar con la complejidad interna si no aporta valor.

## Cuándo delegar
- tareas largas
- investigación separable
- debugging complejo
- implementación aislada
- revisión independiente
- ramas paralelas que realmente ahorran tiempo

## Cuándo no delegar
- respuestas cortas
- un comando o cambio mínimo
- razonamiento fuertemente acoplado
- plumbing mecánico
- tareas donde el coste de resumir supera el trabajo

## Roles reutilizables
- `main` — coordinador y cara visible
- `triage` — clasificación/extracción/routing
- `research` — investigación y síntesis
- `ops` — debugging/incidentes/config
- `implementation` — cambios aislados o coding
- `review` — segunda pasada y validación crítica

## Reglas maduras
### 1. Delegar con brief concreto
Cada subagente debe recibir:
- objetivo
- scope
- límites
- formato de salida
- qué no hacer

### 2. El coordinador no abdica
Delegar no significa dejar de pensar. El coordinador sigue siendo responsable de:
- decidir estructura
- integrar resultados
- detectar contradicciones
- hablar con el usuario

### 3. Limitar capacidades auxiliares
No todos los agentes deben tener `exec`, `browser`, mensajería o herramientas sensibles. Especialmente `triage` y `review` deben operar con carriles estrechos.

### 4. Aislamiento real > organización visual
Un topic no aísla por sí solo. Si una tarea necesita separación real, usar subagente/sesión/workflow explícito.

### 5. Probar el host real
Un diseño bonito puede romper en el host real. Si se endurece sandbox o se cambian capacidades, probar una tarea real antes de declararlo bueno.

## Cost discipline
- no lanzar subagentes por defecto
- mantener pocos roles claros
- evitar enjambres permanentes
- usar el modelo más barato que sirva para el rol
- reservar modelos fuertes para subagentes donde el leverage sea real

## Anti-patrones
- delegar por inseguridad en vez de por arquitectura
- usar demasiados subagentes en tareas medianas
- crear roles difusos que se pisan entre sí
- dejar a un subagente herramientas potentes “por si acaso”
- asumir que una política de sandbox sirve igual en cualquier host
