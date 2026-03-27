# Agent Foundation v1

Base reusable y neutral para crear agentes maduros sin copiar contexto personal, memoria privada ni hacks locales de otro agente.

## Objetivo
Convertir las buenas prácticas ya validadas en Bruno en un sistema portable para futuros agentes como Drasa.

## Cuándo se aplica
`Agent Foundation` **no sustituye** la instalación ni el onboarding inicial de OpenClaw.

Se aplica **después** de que exista un agente limpio y funcional, típicamente cuando ya ocurrió lo siguiente:
- OpenClaw está instalado
- al menos un modelo funciona
- el workspace existe
- ocurrió el bootstrap inicial
- usuario y agente ya tuvieron su primer contacto

Desde ese punto, el agente puede leer `Agent Foundation` y usarlo para estructurarse a sí mismo con una base madura.

## Principios
- Lo reusable vive en archivos, no en prompts gigantes.
- Lo personal/local se separa del core.
- Las reglas deben sobrevivir a cambios de modelo, sesión y compaction.
- Automatización mecánica primero; LLM solo cuando aporte inteligencia real.
- Verificación real antes de declarar éxito.

## Estructura
- `CORE_PRINCIPLES.md` — filosofía operativa reusable
- `MEMORY_SYSTEM.md` — memoria, higiene y continuidad
- `MODEL_ROUTING.md` — routing y fallback de modelos
- `SUBAGENT_POLICY.md` — coordinador, delegación y aislamiento real
- `VERIFICATION.md` — validación y criterio de cierre
- `HOUSEKEEPING.md` — mantenimiento silencioso y healthchecks
- `ERROR_LEARNING.md` — postmortems, lessons y prevención
- `PROMOTION_POLICY.md` — criterio para que una práctica entre al core
- `NEW_AGENT_ADOPTION.md` — cómo instanciar un agente nuevo desde esta base
- `ROUTING_AND_ISOLATION.md` — separación entre organización visible y aislamiento real
- `CHANGELOG.md` — evolución del framework
- `ROADMAP.md` — backlog y mejoras previstas
- `templates/` — plantillas para nuevos agentes

## Capas
### 1. Core reusable
Buenas prácticas que sirven para cualquier agente.

### 2. Personalización local
Identidad, tono, usuario, objetivos y límites del agente concreto.

### 3. Entorno
Topics, workflows, herramientas, integraciones y operaciones del host real.

## Regla importante
No copiar a un nuevo agente:
- datos personales de Narder o Sonia
- memorias privadas
- routing exacto de Bruno
- secretos, hosts o infraestructura sensible

Sí copiar:
- principios maduros
- patrones de operación
- reglas de memoria
- disciplina de costes
- verificación
- aprendizaje de errores

## Uso recomendado
1. Arrancar OpenClaw y dejar un agente limpio y funcional
2. Leer este índice
3. Instanciar plantillas en el nuevo agente/workspace
4. Personalizar solo la capa local
5. Mantener `CHANGELOG.md` y `ROADMAP.md`
6. Promover al core solo prácticas ya probadas
