# Agent Foundation v1

Base reusable y neutral para madurar agentes de OpenClaw después del bootstrap inicial.

## Objetivo
Ayudar a un agente ya funcional a estructurar mejor su operación post-bootstrap.

## Cuándo se aplica
Se aplica cuando el agente ya está vivo y operativo, típicamente con:
- OpenClaw instalado
- al menos un modelo funcionando
- workspace creado
- bootstrap inicial completado
- primer contacto con el usuario ya ocurrido

Desde ese punto, el agente puede leer `Agent Foundation` y usarlo para mejorar su operación.

## Qué cubre
- principios operativos
- sistema de memoria
- model routing
- política de subagentes
- verificación
- housekeeping
- aprendizaje de errores
- loop de aprendizaje con inbox crudo y promoción controlada
- Foundation como fuente canónica para que otros agentes lean/adapten desde el repo
- promoción de soluciones a capacidades durables (`skillify`)
- continuidad ligera por topic/proyecto
- gates deterministas antes de enviar/publicar
- recuperación local-first antes de APIs vivas cuando aplique
- gobernanza de prácticas
- templates de apoyo para operación post-bootstrap

## Estructura
- `CORE_PRINCIPLES.md` — filosofía operativa reusable
- `MEMORY_SYSTEM.md` — memoria, higiene y continuidad
- `MODEL_ROUTING.md` — routing y fallback de modelos
- `SUBAGENT_POLICY.md` — coordinador, delegación y aislamiento real
- `VERIFICATION.md` — validación y criterio de cierre
- `HOUSEKEEPING.md` — mantenimiento silencioso y healthchecks
- `ERROR_LEARNING.md` — postmortems, lessons y prevención
- `LEARNING_LOOP.md` — inbox crudo de aprendizajes y promoción controlada
- `SOURCE_OF_TRUTH.md` — cómo el Foundation vive como fuente canónica para otros agentes
- `PROMOTION_POLICY.md` — criterio para que una práctica entre al core
- `skillify-in-agent-foundation.md` — patrón de promoción de soluciones/fallos a capacidades durables
- `NEW_AGENT_ADOPTION.md` — cómo aplicar esta base a un agente nuevo ya operativo
- `ROUTING_AND_ISOLATION.md` — separación entre organización visible y aislamiento real
- `CHANGELOG.md` — evolución del framework
- `ROADMAP.md` — backlog y mejoras previstas
- `templates/AGENTS_TEMPLATE.md` — apoyo para reglas operativas
- `templates/ROUTING_TEMPLATE.md` — apoyo para routing e aislamiento

## Uso recomendado
1. Leer este índice
2. Revisar principios, memoria, routing y verificación
3. Aplicar la base operativa al workspace del agente
4. Mantener `CHANGELOG.md` y `ROADMAP.md`
5. Promover al core solo prácticas ya probadas
