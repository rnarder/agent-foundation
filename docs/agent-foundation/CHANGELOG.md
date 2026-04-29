# Changelog

## v1.7.0 — 2026-04-29
- Se añadió `LEARNING_LOOP.md` como patrón core para capturar aprendizajes/errores/features en un inbox crudo antes de promoverlos.
- Se añadió `SOURCE_OF_TRUTH.md` para formalizar que Agent Foundation vive como fuente canónica: un agente mantenedor destila aprendizajes al repo común y otros agentes beben de esa fuente para adaptar localmente.
- `MEMORY_SYSTEM.md` incorpora `.learnings/` como capa previa a memoria permanente para evitar inflación de contexto.
- `ERROR_LEARNING.md` distingue entre inbox de triage y postmortems/reglas durables.
- `ADOPTION_FLOW.md` formaliza que ideas externas tipo Hermes/self-improving-agent se adapten localmente, se capturen con coste mínimo y solo se promuevan si demuestran valor real.
- `NEW_AGENT_ADOPTION.md` añade el flujo “beber de la fuente”: leer changelog/docs nuevas y adaptar `AGENTS.md`, skills, memoria y scripts locales sin recetas privadas por agente.

## v1.6.0 — 2026-04-26
- `skillify` dejó de estar solo como propuesta y quedó integrado en el core como disciplina de promoción de soluciones/fallos a capacidades durables.
- `PROMOTION_POLICY.md` añade niveles mínimos de promoción: regla, checklist/doc, script, skill, skill + tests/routing/monitoring.
- `ROUTING_AND_ISOLATION.md` incorpora el patrón de continuidad ligera por topic/proyecto, con límites explícitos para no confundirlo con aislamiento ni convertirlo en log ruidoso.
- `VERIFICATION.md` añade gates deterministas antes de envíos/publicaciones externas con links, archivos, destinatarios o campos estructurados.
- `MEMORY_SYSTEM.md` añade recuperación local-first para historia personal/operativa antes de consultar APIs vivas cuando existan fuentes locales plausibles.
- `ADOPTION_FLOW.md` formaliza cómo adaptar ideas externas sin copiarlas ciegamente y cómo promoverlas a capacidad durable.

## v1.5.0 — 2026-04-26
- Se promovió al Foundation el patrón de **watchdogs conscientes de mantenimiento**: locks, timeouts explícitos, gracia post-boot/post-restart, detección de gestores de paquetes activos y `reboot-required`, y supresión de deuda de fallos durante ventanas legítimas de update/reboot.
- Se añadió el patrón de **update watchers del host** para VPS/servidores: polling determinístico, estado local, dedupe y alertas solo ante cambios o limpieza de estado.
- `ERROR_LEARNING.md` ahora exige RCA mínimo con revisión de logs/crash signatures para no confundir recuperación automática con causa raíz.
- `VERIFICATION.md` añade gates específicos para updates de OS, watchdog/cron y workarounds por variables de entorno.
- `NEW_AGENT_ADOPTION.md` incorpora checks de madurez para agentes en servidores persistentes: update watcher, gateway watchdog y workarounds documentados para plugins no críticos.

## v1.4.0 — 2026-03-28
- Se adoptó y promovió al core el patrón de **progressive disclosure** para memoria/contexto.
- `MEMORY_SYSTEM.md` ahora formaliza recuperación por capas: buscar primero, leer fragmentos mínimos y expandir solo si hace falta.
- `INCUBATING_PRACTICES.md` se actualizó para marcar esta práctica como `adopted-local` y `promoted-core`.

## v1.3.0 — 2026-03-28
- Se añadió `EXTERNAL_PATTERNS_INTAKE.md` para registrar ideas externas antes de tocar el core.
- Se añadió `INCUBATING_PRACTICES.md` para seguir prácticas en prueba con criterios de promoción/descarte.
- Se añadió `ADOPTION_FLOW.md` para formalizar el paso de intake → incubación → adopción local → promoción al core o descarte.
- Se reforzó `ROADMAP.md` con checkpoints de incubación y control de deriva.

## v1.2.0 — 2026-03-28
- Se limpió el scope del framework para alinearlo mejor con su foco post-bootstrap.
- Se retiraron templates fuera de foco (`SOUL_TEMPLATE`, `USER_TEMPLATE`, `BOOTSTRAP_TEMPLATE`).
- Se mantuvieron solo templates operativos relevantes (`AGENTS_TEMPLATE`, `ROUTING_TEMPLATE`).
- Se simplificó el framing para que el repo sea más austero y coherente.

## v1.1.0 — 2026-03-27
- Se añadió gobernanza explícita del framework con `PROMOTION_POLICY.md`.
- Se añadió `NEW_AGENT_ADOPTION.md` para definir cómo instanciar agentes nuevos desde el core.
- Se añadió `ROUTING_AND_ISOLATION.md` para formalizar la separación entre organización visible y aislamiento real.
- Se reforzó el roadmap para tratar `Agent Foundation` como sistema vivo.

## v1.0.0 — 2026-03-27
- Nace `Agent Foundation` como base reusable para futuros agentes.
- Se define separación entre core reusable, personalización local y entorno.
- Se capturan principios de coste, memoria, routing, subagentes, verificación, housekeeping y error learning.
- Se añaden plantillas iniciales para bootstrap de nuevos agentes.
