# Housekeeping

## Objetivo
Mantener el sistema sano con checks baratos, poco ruido y alertas útiles.

## Principios
- checks silenciosos por defecto
- alertas solo si hay cambio o problema
- coste casi cero
- scripts y cron por encima de LLM para mantenimiento mecánico
- el housekeeping debe reducir babysitting, no crear más babysitting

## Áreas típicas
- healthchecks
- watchdogs
- update watchers
- restore kits
- higiene de logs
- higiene de contexto
- revisión de crons/workers
- verificación de integraciones

## Reglas maduras
### 1. El mantenimiento debe ser barato
La mayor parte del housekeeping debería vivir en:
- scripts
- cron
- checks deterministas
- thresholds simples

### 2. Alertar por excepción, no por rutina
No notificar “todo sigue bien” a menos que haya una razón concreta. Lo normal es silencio si nada cambió.

### 3. Restaurar importa más que coleccionar backups
Un restore kit austero y recuperable vale más que un backup opaco que nadie sabe restaurar.

### 4. Reducir deriva operativa
Los checks deben ayudar a detectar:
- crons muertos
- integraciones caídas
- inflación de contexto/logs
- workers colgados
- rutas obsoletas todavía activas

### 5. No depender de LLM para plumbing
Si el housekeeping requiere una llamada de modelo constante para funcionar, probablemente está mal diseñado.

### 6. Watchdogs conscientes de mantenimiento
Un watchdog no debe confundir una ventana legítima de update/reboot con una caída real.

Patrón recomendado:
- usar lock para evitar ejecuciones solapadas
- timeout explícito para healthchecks lentos
- gracia post-boot/post-restart
- detectar gestores de paquetes activos (`apt`, `dpkg`, `unattended-upgrade` o equivalente)
- detectar `reboot-required` o señal equivalente del sistema
- no acumular deuda de fallos durante mantenimiento esperado
- alertar solo si la recuperación falla fuera de la ventana esperada

### 7. Watchers de updates del host
Para hosts remotos o siempre encendidos, un watcher barato de updates debe:
- refrescar metadatos de paquetes de forma determinística
- detectar paquetes pendientes y reboot requerido
- persistir estado local para deduplicar
- avisar solo cuando el estado cambia o se limpia
- no usar LLM para el loop de polling

### 8. Workarounds de runtime deben ser autocurables si son seguros
Si un fallo repetible del runtime tiene un workaround seguro y acotado, el watchdog puede aplicarlo automáticamente **solo** cuando detecta una firma clara del fallo.

Ejemplos de firma clara:
- error exacto en logs
- crash loop con patrón repetido
- plugin no crítico fallando de forma conocida

Requisitos:
- documentar el impacto del workaround
- verificar health tras aplicarlo
- no ocultar fallos desconocidos bajo el workaround
- registrar el incidente en error learning

## Checklist reusable
- ¿hay un check barato y determinista?
- ¿la alerta solo salta si hay cambio/problema?
- ¿el coste es sostenible?
- ¿hay una forma simple de saber si el sistema está sano?
- ¿el mecanismo de recovery está documentado?
- ¿el watchdog distingue mantenimiento esperado de caída real?
- ¿hay dedupe/estado para evitar alertas repetidas?

## Anti-patrones
- healthchecks ruidosos
- alertas redundantes
- crons opacos sin logs ni estado
- sistemas de restore que nunca se prueban
- housekeeping que introduce más complejidad que la que elimina
