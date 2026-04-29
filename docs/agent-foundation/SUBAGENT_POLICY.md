# Subagent Policy

## Principio
Delegar solo cuando el beneficio en foco, aislamiento o paralelismo supera el coste de coordinación.

## Patrón recomendado
- Un coordinador habla con la persona.
- Subagentes especializados trabajan por debajo.
- Los topics/canales organizan; las sesiones/subagentes aíslan de verdad.
- El usuario no debería cargar con la complejidad interna si no aporta valor.
- Elegir bien el tipo de "baby agente": subagente aislado para trabajo acotado, ACP persistente cuando conviene continuidad tipo Codex/Claude/Cursor.

## Cuándo delegar
- tareas largas
- investigación separable
- debugging complejo
- implementación aislada
- revisión independiente
- ramas paralelas que realmente ahorran tiempo
- trabajo que se beneficia de una sesión fresca o de no contaminar el contexto principal
- peticiones explícitas de trabajar en Codex/Claude/Cursor/Gemini u otro harness ACP

## Cuándo no delegar
- respuestas cortas
- un comando o cambio mínimo
- razonamiento fuertemente acoplado
- plumbing mecánico
- tareas donde el coste de resumir supera el trabajo
- cuando el subagente necesitaría volver cada dos minutos a pedir microdecisiones

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
- criterio de parada o de escalado

### 2. Elegir bien el runtime
- Usar subagente aislado para runs acotados y trabajo que solo debe devolver resultado.
- Usar ACP persistente cuando haga falta continuidad, hilo propio o una sesión de coding que viva más de un turno.
- No abrir sesiones persistentes por costumbre, solo cuando la continuidad compense.

### 3. El coordinador no abdica
Delegar no significa dejar de pensar. El coordinador sigue siendo responsable de:
- decidir estructura
- integrar resultados
- detectar contradicciones
- hablar con el usuario
- hacer la verificación final

### 4. Limitar capacidades auxiliares
No todos los agentes deben tener `exec`, `browser`, mensajería o herramientas sensibles. Especialmente `triage` y `review` deben operar con carriles estrechos.

### 5. Aislamiento real > organización visual
Un topic no aísla por sí solo. Si una tarea necesita separación real, usar subagente/sesión/workflow explícito.

### 6. Probar el host real
Un diseño bonito puede romper en el host real. Si se endurece sandbox o se cambian capacidades, probar una tarea real antes de declararlo bueno.

### 7. Pocos agentes, briefs mejores
En tareas medianas, casi siempre gana:
- 1 coordinador
- 1 implementador o investigador
- 1 revisor opcional

Evitar enjambres si la ganancia real es marginal.

## Cost discipline
- no lanzar subagentes por defecto
- mantener pocos roles claros
- evitar enjambres permanentes
- usar el modelo más barato que sirva para el rol
- reservar modelos fuertes para subagentes donde el leverage sea real
- preferir briefs más precisos antes que más subagentes
- cerrar sesiones persistentes que ya no aportan continuidad real

## Anti-patrones
- delegar por inseguridad en vez de por arquitectura
- usar demasiados subagentes en tareas medianas
- crear roles difusos que se pisan entre sí
- dejar a un subagente herramientas potentes “por si acaso”
- asumir que una política de sandbox sirve igual en cualquier host
- usar ACP persistente para trabajo que cabía en un run aislado
- lanzar un baby agente con un prompt vago tipo "mírate esto"
