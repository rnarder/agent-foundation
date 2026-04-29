# New Agent Adoption

## Objetivo
Definir cómo aplicar `Agent Foundation` a un agente nuevo que ya superó el bootstrap inicial y necesita madurar su operación.

## Momento de adopción
Este framework entra en juego cuando el agente ya está funcional y puede empezar a estructurarse mejor.

Precondiciones recomendadas:
- OpenClaw ya instalado
- al menos un modelo ya configurado y funcional
- workspace ya creado
- bootstrap inicial ya completado
- primer intercambio usuario/agente ya ocurrido

A partir de ahí, el agente puede leer `Agent Foundation` desde la fuente canónica actualizada y usarlo como base operativa post-bootstrap.

## Orden recomendado
### 1. Revisar la base
Leer:
- `README.md`
- `CHANGELOG.md`
- `SOURCE_OF_TRUTH.md`
- `CORE_PRINCIPLES.md`
- `MEMORY_SYSTEM.md`
- `MODEL_ROUTING.md`
- `VERIFICATION.md`

### 2. Aplicar la estructura operativa
Usar desde `Agent Foundation`:
- principios core
- sistema de memoria
- routing/model policy reusable
- política de subagentes
- verificación
- housekeeping
- error learning
- plantillas de apoyo

Además, sembrar desde el principio estas prácticas operativas ya maduras:
- clarificación fuerte antes de plan o ejecución cuando haya branching real (`panorama 360`)
- planes anclados a comportamiento deseado, no solo a tareas
- verificación en el seam correcto, no solo en helpers internos
- delegación con criterio: pocos subagentes, briefs mejores, runtime correcto

### 3. Aterrizar en el entorno real
Definir o completar:
- routing local
- herramientas disponibles
- workflows y límites operativos
- prácticas de mantenimiento útiles para el host real
- watcher de updates del host si es VPS/servidor persistente
- watchdog del gateway con gracia de reboot/update y dedupe de alertas
- workaround documentado para plugins no críticos que puedan tumbar el gateway, si aplica
- criterio de cuándo usar sesión principal, subagente aislado o ACP persistente
- repos y fronteras de trabajo si el agente vivirá con repo Git propio

Si el agente parte de un repo Git dedicado, dejar claro desde el inicio:
- qué parte del Foundation vive en el repo reusable / fuente canónica
- qué parte es personalización local del agente
- qué archivos no deben sincronizarse por contener memoria privada o contexto sensible

## Beber de la fuente
Cuando el Foundation evoluciona, un agente no necesita una receta privada por nombre. Debe:
1. leer `CHANGELOG.md`,
2. leer los documentos nuevos o modificados,
3. decidir qué aplica a su entorno,
4. adaptar sus archivos locales (`AGENTS.md`, skills, memoria, scripts) sin copiar memoria privada de otro agente.

Ver `SOURCE_OF_TRUTH.md` para el patrón completo.

### 4. Validar maduración inicial
Checklist mínimo:
- ¿su memoria operativa está clara?
- ¿su routing está claro?
- ¿tiene criterio de verificación?
- ¿sus prácticas operativas viven en archivos?
- ¿su entorno real fue probado?
- ¿sus updates del host no pueden dejarla colgada sin aviso o recovery?
- ¿su gateway watchdog distingue reboot/update de caída real?
- ¿sabe cuándo abrir panorama 360 antes de planificar?
- ¿sus planes describen comportamiento deseado además de pasos?
- ¿su receta de subagentes distingue run aislado vs sesión persistente?
- ¿la separación entre core reusable y contexto privado del agente está clara?

## Regla
Aplicar `Agent Foundation` no es rehacer el nacimiento del agente. Es madurar su operación post-bootstrap con una base reusable, clara y durable.

La meta no es copiar otro agente entero. La meta es transferir doctrina útil y dejar que cada agente concrete su personalidad, su routing local y su entorno real sin mezclar eso con el core reusable.
