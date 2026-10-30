# Error Learning

## Objetivo
Convertir cada error importante en prevención duradera.

## Regla maestra
Un error no termina cuando se arregla. Termina cuando deja una mejora reusable en el sistema.

## Formato mínimo
- Qué pasó
- Por qué pasó
- Qué se cambió
- Qué regla preventiva queda

## Cuándo registrar
- errores repetibles
- regresiones
- malos supuestos
- routing incorrecto
- coste inesperado
- fallos de aislamiento o verificación
- cambios que parecían correctos en teoría y fallaron en el host real

## Tipos de aprendizaje que suelen valer oro
### 1. Supuesto falso
Ejemplo abstracto: asumir que un catálogo de modelos equivale a disponibilidad real.

### 2. Verificación insuficiente
Ejemplo abstracto: aplicar config y no comprobar el estado real tras restart.

### 3. Aislamiento mal entendido
Ejemplo abstracto: asumir que la organización visual separa memoria o ejecución real.

### 4. Complejidad que se volvió en contra
Ejemplo abstracto: endurecer seguridad de una forma que rompe la operativa real del host.

## Dónde queda cada aprendizaje
- regla de comportamiento → `AGENTS.md` del agente
- parte mecánica → script/test (ver `IMPROVEMENT.md`)
- incidente del host, gotcha de herramienta o workaround → registro de incidentes/auditorías del agente
- práctica estructural → doc operativa del agente

Los incidentes del host merecen registro propio aunque sean específicos de un entorno: son justo lo que se necesita la próxima vez que el mismo servicio caiga.

## RCA mínimo para incidentes operativos
Cuando un servicio cae, no basta con arreglar el síntoma visible.

Checklist:
- revisar health/status actual
- revisar logs del servicio alrededor del primer fallo
- distinguir caída real vs ventana legítima de mantenimiento
- buscar crash signatures repetidas
- confirmar si el fix aplicado ataca causa raíz o solo reduce ruido
- documentar corrección si el diagnóstico inicial fue incompleto

Regla: un watchdog que reinicia servicios puede ocultar la causa raíz si no se revisan logs. La recuperación automática es útil, pero la prevención durable exige identificar el patrón que causó la caída.

## Workaround seguro vs deuda oculta
Un workaround operativo puede ser correcto si:
- desactiva solo una capacidad no crítica
- mantiene el acceso principal funcionando
- queda documentado con impacto y rollback
- se verifica en el proceso real, no solo en el archivo de config

No debe convertirse en deuda silenciosa: registrar el workaround y revisar tras cada update si sigue siendo necesario. Un workaround que el upstream ya resolvió se retira.

## Anti-patrones
- arreglar rápido y olvidar
- culpar al modelo sin revisar sistema y contexto
- documentar solo el síntoma, no la causa raíz
- repetir el mismo error porque la regla nunca quedó escrita
