# Memory System

## Objetivo
Tener continuidad útil sin inflación de contexto ni fuga de datos innecesarios.

## Niveles
- `MEMORY.md` — memoria curada de largo plazo
- `memory/YYYY-MM-DD.md` — diario operativo
- `memory/lessons.md` — reglas aprendidas
- `memory/MEMORY_ERRORS.md` — errores, causa raíz y prevención

## Qué va en cada nivel
### `MEMORY.md`
- identidad estable del usuario o entorno si aplica
- objetivos duraderos
- preferencias operativas persistentes
- sistemas ya consolidados

### `memory/YYYY-MM-DD.md`
- decisiones del día
- cambios relevantes
- validaciones importantes
- hechos que podrían perderse con compaction

### `memory/lessons.md`
- reglas de comportamiento corregidas
- patrones que conviene recordar siempre

### `memory/MEMORY_ERRORS.md`
- errores reales
- por qué pasaron
- qué se cambió
- qué regla preventiva queda

## Reglas
- Guardar solo lo que ayude a operar mejor en el futuro.
- No guardar secretos en memoria.
- Resumir decisiones, no volcar ruido.
- Si una corrección cambia el comportamiento futuro, escribirla.
- Si una práctica deja de servir, moverla o retirarla.
- Lo reusable no debe quedar enterrado en un diario diario.

## Protocolo mínimo
### Antes de responder sobre pasado, decisiones o preferencias
- buscar memoria primero
- leer solo lo necesario
- si la confianza es baja, decirlo

### Antes de iniciar una tarea nueva importante
- revisar memoria reciente del día
- confirmar si ya hubo decisiones relacionadas

### Tras cambios relevantes
- escribir una nota breve del cambio
- si deja regla durable, promoverla al archivo correcto

## Higiene
- Preferir notas cortas y accionables.
- Evitar duplicar lo mismo en varios archivos.
- Mantener separación clara entre memoria reusable y memoria personal/local.
- Usar el diario como buffer operativo; usar memoria curada como fuente de verdad.

## Anti-patrones
- usar memoria como log bruto de todo
- guardar conversaciones enteras sin destilar
- responder desde “recuerdo vagamente”
- mezclar información reusable con datos personales de un agente concreto
