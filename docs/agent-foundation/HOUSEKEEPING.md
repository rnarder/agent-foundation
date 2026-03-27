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

## Checklist reusable
- ¿hay un check barato y determinista?
- ¿la alerta solo salta si hay cambio/problema?
- ¿el coste es sostenible?
- ¿hay una forma simple de saber si el sistema está sano?
- ¿el mecanismo de recovery está documentado?

## Anti-patrones
- healthchecks ruidosos
- alertas redundantes
- crons opacos sin logs ni estado
- sistemas de restore que nunca se prueban
- housekeeping que introduce más complejidad que la que elimina
