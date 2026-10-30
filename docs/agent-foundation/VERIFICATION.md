# Verification

Cerrar un trabajo = implementado + comprobado en estado real + documentado si deja aprendizaje reusable. "El comando no dio error" no es evidencia.

## Verificación por tipo de cambio
Para: que cada tipo de cambio tenga su prueba concreta.
- **config patch**: releer el estado real tras el restart (modelos, agentes, fallbacks efectivos)
- **update de OpenClaw**: release notes, `openclaw status`, config afectada, workarounds aún necesarios
- **reboot / update del sistema**: kernel y versión activos, reboot pendiente o no, health de gateway y canales pasada la ventana post-boot, logs si hubo restart loop aunque el health esté verde
- **watchdog / cron**: validar sintaxis (`bash -n`, `py_compile`), ejecutar una vez a mano, instalado exactamente una vez, estado/log local, sin alertas duplicadas en estado estable
- **variable de entorno como workaround**: archivo donde persiste, proceso real que la recibe (`/proc/<pid>/environ`), reiniciar solo el servicio necesario, firma del fallo desaparecida, impacto y rollback documentados
- **seguridad / sandbox**: probar un flujo real en el host, no solo la config
- **routing / modelos**: disponibilidad y coste reales, una tarea real del rol afectado
Verificar: el cierre de cada cambio cita la evidencia de su línea.

## Gate antes de enviar fuera
Para: que links, archivos y destinatarios salgan correctos.
- payload con links, archivos, adjuntos o campos estructurados → check determinista antes de enviar
- links alcanzables (o marcados como no verificados), archivos existentes y no vacíos, destinatario/canal/thread correcto, campos requeridos completos, formato del canal, sin secretos ni contexto privado
Verificar: un envío con un link roto o un archivo vacío se bloquea antes de salir.

## Revisión tras capacidad degradada
Para: que lo hecho con menos capacidad no quede como decisión durable sin revisar.
- degradada = modelo fallback o menor, contexto parcial, herramientas críticas ausentes, sesión aislada sin verificaciones normales
- trabajo sensible o durable hecho así → revisión con la capacidad adecuada: decisiones, archivos/config tocados, acciones externas, evidencia usada, qué aceptar o repetir
Verificar: ninguna decisión durable tomada en fallback queda sin esa revisión.
