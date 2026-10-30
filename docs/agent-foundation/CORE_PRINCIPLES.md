# Core Principles

## Lo mecánico sale del modelo
Para: menos coste y resultados repetibles.
- tarea mecánica (lookup, parseo, fechas, filtros, dedupe, validaciones, health checks, polling) → script, cron o check determinista
- al corregir un fallo repetible, extraer su parte mecánica a script o test; en el modelo queda solo el juicio: síntesis, priorización, ambigüedad, tradeoffs
Verificar: ningún cron, heartbeat o loop periódico llama a un modelo para trabajo determinista.

## Panorama 360 antes de cambios importantes
Para: no romper lo que ya funciona al tocar arquitectura, config, routing o automatizaciones.
- antes de cambiar: estado actual, restricciones, opciones y tradeoffs
Verificar: el cambio deja escrito qué había antes y por qué se eligió la opción.

## Investigar hasta aplicar
Para: que investigar acabe en un cambio verificado.
- ante un problema repetido o incierto, fuentes primarias antes que ensayo y error
- ciclo: investigar → entender → adaptar → aplicar → verificar
- cuenta solo si cambia una decisión, workflow, artefacto o gate y demuestra valor en el camino real
- las fuentes de verdad del proyecto prevalecen sobre referencias externas
Verificar: cada investigación cerrada apunta al cambio que produjo.

## Historia local antes que APIs vivas
Para: responder sobre el pasado con menos coste, menos credenciales en juego y con el porqué de las decisiones.
- exports, notas y estado local primero; API viva solo si falta información o hace falta estado actual
Verificar: una pregunta sobre un evento pasado se responde sin llamar a la API viva cuando hay fuente local.

## Catálogo ≠ plan real
Para: no diseñar sobre modelos, providers o features que el plan no cubre.
- disponible en catálogo, ruta válida y coste aceptable son tres comprobaciones distintas
- una mejora teórica no vale en el host hasta probarla allí
