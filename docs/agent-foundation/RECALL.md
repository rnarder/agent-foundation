# Recall

## Objetivo
Responder sobre el pasado con evidencia, no con recuerdo vago, y sin llamar a sistemas externos cuando la respuesta ya está en local.

## Regla maestra
Antes de afirmar algo sobre trabajo previo, decisiones, preferencias, fechas, personas o pendientes: buscar, leer el fragmento mínimo y decir la confianza si las fuentes son parciales.

## Local-first antes de APIs vivas
Cuando existan archivos, exports, diarios o índices plausibles, consultarlos antes que la API viva.

Patrón:
1. buscar en memoria/exports locales
2. leer fragmentos mínimos
3. usar API viva solo si la información local no existe, está incompleta o hace falta estado actual
4. explicar la confianza si las fuentes son parciales

Ejemplos:
- viajes/eventos pasados: calendario exportado o notas antes de API viva
- decisiones antiguas: memoria/sesiones antes de inferir
- facturación/historial operativo: diarios/estado local antes de sistemas externos

## Por qué
- menos coste y latencia
- menos superficie de credenciales y rate limits
- la historia local suele incluir contexto (por qué se decidió algo) que la API viva no tiene

## Anti-patrones
- responder desde "recuerdo vagamente"
- inventar una fecha, cifra o acuerdo que las fuentes no sostienen
- llamar APIs vivas para historia cuando hay fuentes locales suficientes
- cargar contexto de más "por si acaso" en lugar de buscar y leer lo justo
