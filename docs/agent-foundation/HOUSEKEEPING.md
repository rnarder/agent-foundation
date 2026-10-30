# Housekeeping

## Watchdog consciente de mantenimiento
Para: detectar gateway colgado sin crash, canales caídos o health degradado, sin actuar durante un update o reboot.
- script periódico con lock y timeout en el healthcheck
- gracia tras boot y tras cada reinicio
- mantenimiento = `apt`/`dpkg`/`unattended-upgrade` activos o `reboot-required`; durante mantenimiento, contador de fallos a cero
- reinicio tras N fallos, con cooldown
- alerta solo si el reinicio no recupera el health
- un reinicio no cierra el incidente: revisar logs (ver `ERROR_LEARNING.md`)
Verificar: `bash -n`, ejecución manual, instalado una sola vez, silencio con gateway sano, fallo suprimido con `apt` activo.

## Watcher de updates del sistema
Para: saber qué paquetes y reboots tiene pendientes el host.
- script diario determinista
- estado local para deduplicar
- aviso solo cuando el estado cambia o se limpia
Verificar: la primera ejecución crea el estado; la segunda, sin cambios, no avisa.

## Workarounds autocurables
Para: recuperar sin intervención un fallo ya diagnosticado.
- aplicar solo ante su firma exacta (error en logs, crash loop con patrón conocido)
- documentar impacto y rollback; registrar cada aplicación como incidente
- revisar tras cada update de OpenClaw; retirar si el upstream lo resolvió
Verificar: el proceso real recibe el cambio (`/proc/<pid>/environ` si es variable de entorno) y la firma desaparece de los logs.

## Detección de deriva
Para: ver a tiempo lo que se degrada en silencio.
- checks deterministas de: crons muertos, integraciones caídas, workers colgados, inflación de logs o contexto, rutas obsoletas aún activas
- silencio si nada cambió; alerta solo por cambio o problema
Verificar: un cron parado a propósito aparece en el siguiente check.

## Restore probado
Para: volver a un estado bueno en minutos.
Verificar: el restore se ha ejecutado al menos una vez de principio a fin.
