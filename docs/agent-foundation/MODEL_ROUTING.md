# Model Routing

## Principio
El routing debe basarse en modelos realmente validados para el setup activo, no en suposiciones ni en catálogos ajenos al plan real.

## Orden de decisión
1. ¿Hace falta LLM?
2. Si sí, ¿qué nivel de inteligencia hace falta?
3. ¿Qué modelos están realmente disponibles y cubiertos por el setup real?
4. ¿Qué fallback mantiene continuidad sin disparar coste o riesgo?

## Regla base
### Sin LLM
Usar scripts, reglas, cron o validaciones cuando la tarea sea mecánica.

### Modelo pequeño/rápido
Usarlo para:
- triage
- clasificación
- extracción estructurada
- normalización ligera

### Modelo principal
Usarlo para:
- conversación útil normal
- síntesis
- decisiones operativas normales
- análisis moderado

### Modelo fuerte / premium
Reservarlo para:
- debugging complejo
- análisis arquitectónico
- decisiones delicadas
- trabajo donde la calidad adicional compense de verdad

## Reglas maduras
- Disponible en catálogo != incluido en el plan actual.
- Ruta/provider válido != coste aceptable.
- Un fallback debe elegirse por calidad y coste, no solo por disponibilidad.
- Si el modelo principal falla, degradar con elegancia.
- Avisar si el fallback cambia calidad, latencia o coste de forma relevante.
- Mantener la política en archivos del workspace.

## Patrón reusable por roles
- `triage`: barato/rápido
- `main`: modelo principal
- `ops`: modelo fuerte y fiable
- `review`: modelo estable para segunda pasada
- `research`: calidad suficiente para síntesis e investigación, con coste controlado

## Checklist antes de promocionar un modelo al flujo normal
- ¿está realmente disponible en este host/provider?
- ¿está cubierto por el plan/coste real?
- ¿se probó en una tarea real?
- ¿la medición atribuida al modelo está aislada de actividad concurrente en la misma cuenta?
- ¿su comportamiento encaja con el rol propuesto?
- ¿el fallback posterior sigue teniendo sentido?

## Anti-patrones
- diseñar el routing desde marketing o pricing teórico
- mezclar providers distintos como si costaran lo mismo
- meter modelos premium en automático
- dejar fallbacks baratos pero poco fiables sin guardrails
- asumir que lo que sirve en un agente sirve en todos
