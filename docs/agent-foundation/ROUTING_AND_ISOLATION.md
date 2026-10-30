# Routing and Isolation

## Aislamiento explícito
Para: que la separación sea real cuando importa.
- canales, topics, labels y carpetas = organización y delivery
- sesiones, subagentes y workflows explícitos = aislamiento de contexto, memoria y herramientas
- patrón: el topic elige política inicial → el coordinador decide complejidad y rol → si hace falta, delega a sesión/subagente → el resultado vuelve al lugar de delivery
- la política de routing vive en archivos del workspace
Verificar: el routing escrito dice, por canal/topic, comportamiento por defecto, cuándo delegar y dónde llegan las alertas.

## Continuidad ligera por topic/proyecto
Para: no perder decisiones y pendientes de cada proyecto sin inflar la memoria global.
- un archivo corto por topic/proyecto: decisiones activas, pendientes reales, reglas locales, último checkpoint
- actualizar solo ante decisión, cierre, bloqueo, regla durable o checkpoint
- sin secretos y sin mantenimiento con LLM
Verificar: cada archivo cabe en una lectura rápida y no contiene logs de chat.
