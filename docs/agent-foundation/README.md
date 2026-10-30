# Agent Foundation

Doctrina general y reusable para agentes de OpenClaw. Se aplica justo después del bootstrap nativo: cuando el usuario se ha presentado y el agente ha completado su rutina de nacimiento.

## Qué cubre
- principios operativos (mecánico antes que LLM, panorama 360, investigar antes de reinventar)
- recall honesto y local-first
- routing de modelos por coste y plan real
- política de subagentes y briefs
- verificación y gates deterministas antes de envíos externos
- mantenimiento del host: watchdogs conscientes de mantenimiento y watchers de updates
- RCA de incidentes y workarounds documentados
- continuidad ligera por topic/proyecto
- cómo convertir errores e ideas externas en mejoras durables

## Qué no cubre
Identidad, memoria, preferencias del usuario, credenciales, hosts, rutas y canales. Eso es de cada agente.

## Estructura
- `START_HERE.md` — cómo aplicarlo a un agente, paso a paso
- `CORE_PRINCIPLES.md` — filosofía operativa
- `RECALL.md` — recuperación honesta y local-first
- `MODEL_ROUTING.md` — routing y fallback de modelos
- `SUBAGENT_POLICY.md` — coordinador, delegación y aislamiento real
- `VERIFICATION.md` — validación, gates y criterio de cierre
- `HOUSEKEEPING.md` — mantenimiento silencioso, watchdogs y watchers
- `ERROR_LEARNING.md` — RCA, postmortems y workarounds
- `ROUTING_AND_ISOLATION.md` — organización visible vs aislamiento real; continuidad por topic
- `IMPROVEMENT.md` — de idea o error a mejora durable
- `CHANGELOG.md` — evolución del Foundation
- `templates/AGENTS_TEMPLATE.md` — reglas operativas de partida
- `templates/ROUTING_TEMPLATE.md` — routing y aislamiento

## Uso
Empezar por `START_HERE.md`.
