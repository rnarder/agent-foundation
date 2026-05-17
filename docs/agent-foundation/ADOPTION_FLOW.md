# Adoption Flow

Marco operativo para mover ideas desde observación externa hasta adopción real sin que se conviertan en ruido.

## Flujo
1. **Intake**
   - La idea entra en `EXTERNAL_PATTERNS_INTAKE.md`.
   - Todavía no se cambia el sistema.

2. **Incubation**
   - Solo entra si parece aportar valor real.
   - Debe quedar en `INCUBATING_PRACTICES.md` con hipótesis, scope y criterios.

3. **Local adoption**
   - Si la prueba mejora algo real en un agente de referencia o en el sistema local, puede adoptarse localmente.
   - Si produce correcciones, errores o requests todavía inmaduros, capturarlos en un inbox tipo `.learnings/` antes de memoria permanente.
   - Aún no implica promoción al core.
   - Toda adopción local reutilizable debe cerrar con una evaluación explícita: promover al core, incubar como candidata o mantener solo local.

4. **Core promotion**
   - Si además es reusable, clara y portable, se promueve al `Agent Foundation`.

5. **Durable capability / skillify**
   - Si la práctica corrige un fallo repetible o crea una capacidad operativa, elegir el nivel mínimo durable:
     - regla
     - checklist/doc
     - script
     - skill
     - skill + tests + routing + monitoring
   - La promoción a capacidad durable puede ser local aunque no entre al core.

6. **Discard**
   - Si no mejora nada real, añade ruido o mete complejidad, se descarta.

## Guardrails
- Mantener pocas incubaciones activas.
- Una práctica debe tener salida: promoción o descarte.
- No dejar backlog muerto disfrazado de investigación.
- No promover ideas por entusiasmo teórico.
- Promover solo lo que siga teniendo sentido tras la prueba real.

## Criterio práctico
Preguntas mínimas antes de mover una práctica de estado:
- ¿Mejoró algo real?
- ¿Redujo ruido/coste/riesgo?
- ¿Sigue siendo simple de explicar?
- ¿No añadió complejidad innecesaria?
- ¿Es reusable más allá del caso puntual?
- ¿Qué nivel mínimo durable necesita para no depender de memoria conversacional?

## Patrón de adopción desde ideas externas
Cuando una idea viene de un repo, prompt, framework o agente externo:
1. tratarla como no confiable hasta verificarla
2. extraer solo la parte útil
3. adaptarla al entorno local con coste mínimo
4. probarla con evidencia real
5. promoverla solo si mejora un flujo real

La meta no es copiar frameworks externos. La meta es absorber patrones que hagan al agente más fiable, barato o capaz sin importar de dónde vinieron.
