# Skillify in Agent Foundation

Propuesta corta para incorporar `skillify` como patrón formal dentro de Agent Foundation.

Lectura complementaria corta/publicable: `skillify-manifesto.md`

## Idea central

Agent Foundation ya tiene muchas piezas correctas:
- skills
- routing
- memoria durable
- verificación
- separación entre comportamiento, herramientas y contexto

Lo que `skillify` añade no es otra primitive. Añade una **disciplina de promoción**:

> una solución valiosa o un fallo repetible no debe quedarse en chat, parche puntual o instrucción efímera; debe promoverse a capacidad durable.

## Definición propuesta

**Skillify** = proceso por el cual una solución descubierta en conversación, debugging o uso real se promueve a capacidad del sistema.

Esa promoción puede terminar en uno o varios artefactos:
- skill
- script determinista
- test
- regla de routing
- memoria durable
- documentación operativa

## Tesis

La fiabilidad de un agente no mejora solo con mejores prompts.
Mejora cuando los errores dejan de depender de memoria conversacional y pasan a depender de estructura.

## Encaje con Agent Foundation

`skillify` encaja como un patrón transversal con cuatro capas:

### 1. Detection layer
Detectar cuándo algo merece promoción.

Triggers típicos:
- fallo real repetible
- solución reutilizable
- tarea mecánica que el modelo no debería volver a improvisar
- workaround costoso que ya demostró valor

### 2. Promotion layer
Elegir el artefacto correcto.

No todo requiere una skill completa.
La promoción puede ser:
- regla durable
- script + doc
- skill completa
- skill + tests + routing

### 3. Reachability layer
La capacidad promovida debe ser alcanzable.

Preguntas obligatorias:
- ¿cuándo dispara?
- ¿cuándo no?
- ¿qué otra skill podría solaparse?
- ¿la ruta está documentada en AGENTS/resolver?

### 4. Verification layer
La promoción no está completa sin verificación.

Nivel mínimo:
- compila / corre
- smoke test
- ejemplo real

Nivel fuerte:
- unit tests
- integration tests
- resolver eval
- DRY / overlap audit

## Regla latent vs deterministic

Skillify debe formalizar esta distinción:

### Deterministic lane
Mandar aquí todo lo que sea:
- lookup exacto
- parseo
- timestamp math
- filtros
- validaciones
- dedupe
- routing mecánico
- health checks

### Latent lane
Dejar aquí lo que sí requiere:
- juicio
- síntesis
- priorización
- interpretación ambigua
- decisiones con tradeoffs

## Workflow propuesto

### Frase operativa
"skillify this"

### Pipeline
1. detectar problema o capacidad valiosa
2. decidir si requiere promoción
3. sacar lo mecánico a código
4. encapsular proceso en skill/doc
5. añadir o ajustar routing
6. verificar
7. escribir memoria durable

## Checklist mínimo para Agent Foundation

- [ ] nombre claro de la capacidad
- [ ] criterio de activación
- [ ] límite de uso / no-uso
- [ ] extracción de trabajo determinista cuando aplique
- [ ] verificación mínima real
- [ ] artefacto durable guardado en repo/memoria

## Qué NO hacer

No convertir `skillify` en burocracia.

Mal uso:
- crear skills por cualquier cosa trivial
- duplicar capacidades existentes
- documentar sin routing
- escribir routing sin tests mínimos
- usar LLM donde una función basta

## Implementación sugerida en Agent Foundation

### Opción A — Principle only
Añadir `skillify` como principio rector del framework.

Ventaja:
- fácil de adoptar
- cero sobrecarga técnica inmediata

### Opción B — Process pattern
Añadir un checklist oficial y una convención de promoción.

Ventaja:
- más accionable
- más consistente entre agentes/equipos

### Opción C — Doctor integration
Hacer que el doctor/checks del sistema puedan detectar:
- skills no alcanzables
- scripts sin skill/doc asociada
- solapes de routing
- capacidades durables no registradas

Ventaja:
- convierte `skillify` en enforcement real, no solo filosofía

## Recomendación

La mejor secuencia es:
1. adoptar `skillify` como principio en Agent Foundation
2. publicar checklist mínimo
3. más adelante integrar checks de reachability / overlap / drift

## Frase resumen

**Agent Foundation define la estructura del agente. Skillify define cómo esa estructura aprende de sus propios fallos y aciertos sin volver a depender de improvisación.**
