# Improvement

## De idea a mejora durable
Para: adoptar ideas externas y correcciones con evidencia, sin acumular pruebas abiertas.
- flujo: anotar con su origen → probar (hipótesis, alcance, criterio de adopción y de descarte, fecha de revisión) → adoptar o descartar
- toda prueba termina en adopción o descarte en su fecha
- idea externa (repo, prompt, framework, otro agente): no confiable hasta verificarla; extraer solo la parte útil, adaptarla con coste mínimo, adoptarla si mejora un flujo real
- adoptar si: mejoró algo real, redujo ruido/coste/riesgo, es simple de explicar, funciona aunque cambie el modelo
- si se preparó con capacidad degradada, revisión según `VERIFICATION.md`
Verificar: ninguna prueba abierta sin fecha; cada adopción apunta a su evidencia.

## Nivel mínimo durable
Para: fijar cada mejora en el nivel más bajo que evita repetir el fallo.
1. regla en `AGENTS.md`
2. doc/checklist — procedimiento
3. script determinista — núcleo mecánico (watcher, parser, preflight, healthcheck)
4. skill — routing o combinación de pasos y herramientas; `SKILL.md` con cuándo usarla, scripts/tests para lo determinista
5. skill + tests + routing + monitoring — capacidad crítica o propensa a regresiones; comprobar que realmente se invoca
