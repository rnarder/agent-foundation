# Verification

## Regla maestra
No declarar éxito sin evidencia real.

## Qué significa verificar
Verificar no es repetir la intención del cambio. Es comprobar el estado real, el comportamiento real o el resultado observable después del cambio.

## Verificaciones mínimas
- cambio aplicado en config/archivo
- estado real tras restart o patch
- modelo/agente/fallback efectivo
- resultado observable cuando corresponda
- si hay dependencia externa, indicarlo claramente

## Casos importantes
### Tras `config.patch`
- revisar estado real
- revisar modelos/agentes/fallbacks reales
- no asumir que el patch sobrevivió al restart si no se verificó

### Tras updates
- revisar changelog/release notes
- revisar `openclaw status`
- revisar config afectada
- proponer mejoras solo si aportan valor real
- si hubo reboot, confirmar kernel/versión activa y ausencia/presencia de reboot pendiente
- comprobar health del gateway/canales después de la ventana post-boot
- revisar logs recientes si hubo restart loop, aunque el health ya esté verde

### Tras cambios de watchdog/cron
- ejecutar el script manualmente una vez
- validar sintaxis antes de instalarlo (`bash -n`, `py_compile`, etc.)
- confirmar que el cron quedó instalado exactamente una vez
- revisar estado/log local del watcher
- probar que no emite alertas duplicadas en estado estable

### Tras workarounds por variable de entorno
- verificar el archivo donde se persistió la variable
- verificar que el proceso real la recibió (`/proc/<pid>/environ` o equivalente)
- reiniciar solo el servicio necesario
- revisar logs para confirmar que la firma del fallo desapareció
- documentar impacto y rollback

### Antes de enviar/publicar hacia afuera
Usar un gate determinista cuando el payload tenga links, archivos, adjuntos o campos estructurados.

Checklist mínimo:
- links alcanzables o explícitamente no verificados
- archivos existen y no están vacíos
- destinatario/canal/thread correcto
- campos requeridos completos
- formato esperado por el canal/API
- no incluir secretos o contexto privado accidentalmente

Este patrón debe ser script/checklist antes que LLM cuando la validación sea mecánica.

### Tras endurecer seguridad/sandbox
- confirmar compatibilidad con el host real
- probar un flujo real, no solo la config
- si rompe la operativa, ajustar sin perder el principio

### Tras cambiar routing/modelos
- validar disponibilidad real
- validar coste/plan real si aplica
- probar una tarea real del rol afectado

### Tras trabajar con capacidad degradada
Si una tarea sensible o durable se ejecutó bajo una capacidad degradada, no aceptar el cierre sin revisión fuerte.

Capacidad degradada incluye:
- modelo fallback o menor al previsto
- contexto incompleto o recuperado parcialmente
- herramientas críticas no disponibles
- sesión aislada sin acceso a verificaciones normales

Checklist mínimo de revisión:
- qué decisiones se tomaron
- qué archivos/config/capacidades se tocaron
- si hubo acciones externas o irreversibles
- qué evidencia se usó
- qué debe aceptar, corregir o repetir el modelo/agente fuerte

Un modelo barato puede preparar evidencia. La decisión durable debe revisarse con la capacidad adecuada.

## Patrón de verificación barato y fiable
1. aplicar cambio
2. revisar estado real
3. ejecutar prueba pequeña representativa
4. documentar si deja una regla reusable

## Criterio de cierre
Un trabajo termina cuando:
- está implementado
- está verificado
- está documentado si deja aprendizaje reusable

## Anti-patrones
- "debería funcionar"
- "el comando no dio error, así que está bien"
- declarar éxito con solo una prueba teórica
- no revisar side effects tras restart/config patch
- no actualizar documentación/memoria cuando el aprendizaje es durable
