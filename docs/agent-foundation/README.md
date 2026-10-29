# Agent Foundation v2

Doctrina reusable para madurar agentes de OpenClaw después del bootstrap inicial.

## Objetivo
Transferir a un agente ya funcional las prácticas que demostraron valor en operación real: criterio, verificación, mantenimiento del host y gobernanza de mejoras.

## Cuándo se aplica
Cuando el agente ya está vivo y operativo, típicamente con:
- OpenClaw instalado
- al menos un modelo funcionando
- workspace creado
- bootstrap inicial completado
- primer contacto con el usuario ya ocurrido

## Qué cubre
- principios operativos (mecánico antes que LLM, panorama 360, investigar antes de reinventar)
- recuperación honesta y local-first de historia
- model routing por coste y plan real
- política de subagentes y briefs
- verificación y gates deterministas antes de envíos externos
- housekeeping del host: watchdogs conscientes de mantenimiento y watchers de updates
- RCA de incidentes y workarounds documentados
- continuidad ligera por topic/proyecto
- gobernanza: intake de ideas externas, incubación, promoción y descarte

## Estructura
- `CORE_PRINCIPLES.md` — filosofía operativa reusable
- `RECALL.md` — recuperación honesta y local-first antes de APIs vivas
- `MODEL_ROUTING.md` — routing y fallback de modelos
- `SUBAGENT_POLICY.md` — coordinador, delegación y aislamiento real
- `VERIFICATION.md` — validación, gates y criterio de cierre
- `HOUSEKEEPING.md` — mantenimiento silencioso, watchdogs y watchers
- `ERROR_LEARNING.md` — RCA, postmortems y workarounds
- `ROUTING_AND_ISOLATION.md` — organización visible vs aislamiento real; continuidad por topic
- `PROMOTION_POLICY.md` — criterio para que una práctica entre al core y nivel mínimo durable
- `ADOPTION_FLOW.md` — de idea externa a adopción real
- `EXTERNAL_PATTERNS_INTAKE.md` — registro de ideas externas evaluadas
- `INCUBATING_PRACTICES.md` — prácticas en prueba
- `SOURCE_OF_TRUTH.md` — cómo el Foundation vive como fuente canónica
- `NEW_AGENT_ADOPTION.md` — cómo aplicar esta base a un agente nuevo
- `CHANGELOG.md` — evolución del framework
- `ROADMAP.md` — backlog
- `templates/AGENTS_TEMPLATE.md` — reglas operativas de partida
- `templates/ROUTING_TEMPLATE.md` — routing y aislamiento

## Uso recomendado
1. Leer este índice y `CORE_PRINCIPLES.md`
2. Revisar verificación, housekeeping y routing
3. Adaptar al workspace del agente lo que aplique a su host y su usuario
4. Mantener `CHANGELOG.md` y `ROADMAP.md`
5. Promover al core solo prácticas ya probadas
