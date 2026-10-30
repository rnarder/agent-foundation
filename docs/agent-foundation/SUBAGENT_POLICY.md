# Subagent Policy

## Cuándo delegar
Para: delegar solo cuando el foco, el aislamiento o el paralelismo pagan la coordinación.
- sí: tareas largas, investigación separable, debugging complejo, implementación aislada, revisión independiente, ramas paralelas que ahorran tiempo, trabajo que se beneficia de contexto fresco, petición explícita de un harness (Codex/Claude/Cursor/Gemini)
- no: respuestas cortas, un comando, razonamiento muy acoplado, plumbing mecánico, cuando resumir cuesta más que hacer, cuando el subagente necesitaría microdecisiones constantes
- en tareas medianas: 1 coordinador + 1 implementador o investigador + revisor opcional

## Runtime
Para: no pagar continuidad que no se usa.
- subagente aislado: run acotado que solo devuelve resultado
- ACP persistente: continuidad, hilo propio o sesión de coding de más de un turno
- cerrar sesiones persistentes que ya no aportan continuidad

## Capacidades y coste
Para: limitar riesgo y gasto por rol.
- cada rol con las herramientas mínimas; `research` y `review` sin `exec`, browser ni mensajería salvo necesidad
- un agente separado solo si aporta herramientas, contexto o permisos distintos; el triage mecánico es del router determinista/main
- el modelo más barato que sirva para el rol; fuertes solo donde haya leverage
Verificar: tras cambiar sandbox o capacidades, una tarea real del rol funciona en el host.
