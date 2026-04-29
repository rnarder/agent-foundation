# Memory System

## Objetivo
Tener continuidad útil sin inflación de contexto ni fuga de datos innecesarios.

## Niveles
- `.learnings/` — inbox crudo de aprendizajes, errores y feature requests antes de promoción
- `MEMORY.md` — memoria curada de largo plazo
- `memory/YYYY-MM-DD.md` — diario operativo
- `memory/lessons.md` — reglas aprendidas
- `memory/MEMORY_ERRORS.md` — errores, causa raíz y prevención

## Qué va en cada nivel
### `.learnings/`
- correcciones y aprendizajes aún sin decidir
- errores no necesariamente graves
- capacidades pedidas o patrones incipientes
- entradas cortas, redactadas y sin secretos

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
- Capturar en inbox crudo primero cuando no esté claro si algo merece memoria permanente.

## Progressive disclosure
La memoria debe recuperarse por capas, no volcarse de golpe.

### Patrón recomendado
1. **Buscar primero**
   - localizar dónde podría estar el contexto relevante
2. **Leer fragmentos mínimos**
   - traer solo las líneas/snippets necesarios para validar o responder
3. **Expandir solo si hace falta**
   - si persisten dudas o falta contexto, leer un poco más
4. **Evitar contexto sobrante**
   - no cargar memoria de más “por si acaso”

### Objetivo operativo
- reducir inflación de contexto
- mantener precisión
- mejorar coste/claridad
- traer solo lo necesario para la tarea actual

## Protocolo mínimo
### Antes de responder sobre pasado, decisiones o preferencias
- buscar memoria primero
- leer solo lo necesario
- si la confianza es baja, decirlo

### Antes de consultar APIs vivas para historia personal/operativa
Preferir recuperación local-first cuando existan archivos, exports, diarios o índices plausibles.

Patrón:
1. buscar memoria/exports locales
2. leer fragmentos mínimos
3. usar API viva solo si la información local no existe, está incompleta o necesita estado actual
4. explicar la confianza si las fuentes son parciales

Ejemplos:
- viajes/eventos pasados: calendario exportado o notas antes de API viva
- decisiones antiguas: memoria/sesiones antes de inferir
- facturación/historial operativo: diarios/estado local antes de sistemas externos

### Antes de iniciar una tarea nueva importante
- revisar memoria reciente del día
- confirmar si ya hubo decisiones relacionadas

### Tras cambios relevantes
- escribir una nota breve del cambio
- si deja regla durable, promoverla al archivo correcto
- si aún necesita triage, dejarla primero en `.learnings/`

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
- cargar contexto excesivo antes de comprobar si realmente hace falta
- llamar APIs vivas para historia cuando hay fuentes locales suficientes
