# Model Routing

## Modelo por tarea según el plan real
Para: cada tarea con el modelo justo, sin coste ni riesgo de más.
- orden: ¿hace falta LLM? → ¿qué nivel? → ¿qué modelos cubre el plan real? → ¿qué fallback mantiene continuidad?
- sin LLM: tareas mecánicas
- pequeño/rápido: triage, clasificación, extracción estructurada, normalización
- principal: conversación, síntesis, decisiones operativas normales
- fuerte: debugging complejo, arquitectura, decisiones delicadas
- por rol: `triage` barato, `main` principal, `ops` fuerte y fiable, `review` estable, `research` suficiente con coste controlado
- modelos premium nunca en automático
- la política vive en archivos del workspace
Verificar: el routing está escrito y cada modelo del flujo normal pasó por la checklist de abajo.

## Promocionar un modelo al flujo normal
- disponible en este host/provider
- cubierto por el plan/coste real
- probado en una tarea real del rol
- medición aislada de actividad concurrente en la misma cuenta
- el fallback posterior sigue teniendo sentido

## Fallback
Para: continuidad sin sorpresas.
- elegido por calidad y coste, no solo por disponibilidad
- avisar si el fallback cambia calidad, latencia o coste de forma relevante
- lo hecho en fallback pasa por la revisión de `VERIFICATION.md`
