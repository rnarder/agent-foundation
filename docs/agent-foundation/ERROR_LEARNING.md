# Error Learning

## RCA de incidentes
Para: que cada caída o error importante deje causa raíz y prevención.
- registrar: errores repetibles, regresiones, supuestos falsos, routing incorrecto, coste inesperado, fallos de aislamiento o verificación, cambios que fallaron en el host real
- formato: qué pasó · por qué · qué se cambió · qué prevención queda
- incidente de servicio: health actual, logs alrededor del primer fallo, ¿mantenimiento legítimo o caída real?, firmas repetidas, ¿el fix ataca la causa o solo el ruido?
- un reinicio automático recupera, no explica: revisar logs igualmente
- destino: parte mecánica → script/test; regla → `AGENTS.md` o skill; incidente del host, gotcha o workaround → registro de incidentes del agente (aunque sea específico del entorno)
- workaround aceptable: desactiva solo algo no crítico, mantiene el acceso principal, documentado con impacto y rollback, verificado en el proceso real; revisarlo tras cada update y retirarlo si el upstream lo resolvió
Verificar: cada incidente registrado tiene causa raíz y una prevención concreta (script, test, gate o regla).
