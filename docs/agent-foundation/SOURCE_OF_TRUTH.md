# Agent Foundation as Source of Truth

## Objetivo
`Agent Foundation` debe vivir como fuente canónica en su repo/documentación reusable. Un agente mantenedor lo actualiza cuando una práctica local demuestra valor —por ejemplo el learning loop inspirado en self-improving-agent/Hermes— y otros agentes lo leen desde esa fuente para adaptar lo que corresponda a su propio entorno.

## Principio
El Foundation no es una receta privada por agente. Es la fuente común.

Cada agente debe “beber de la fuente”:
1. sincronizar o leer el Foundation actualizado,
2. revisar `CHANGELOG.md` para entender qué cambió,
3. leer los documentos nuevos o modificados,
4. decidir qué aplica a su caso,
5. adaptar su `AGENTS.md`, skills, memoria y scripts locales sin copiar memoria privada de otro agente.

## Flujo canónico

### 1. Aprendizaje local
Un agente descubre o valida una práctica útil en su operación real.

Ejemplos:
- una corrección de usuario que evita errores futuros
- un patrón externo que mejora fiabilidad o coste
- una automatización que deja de depender del modelo
- una verificación que evita falsos positivos

### 2. Destilación
El agente reduce el aprendizaje a doctrina reusable:
- qué problema resuelve
- cuándo usarlo
- cuándo no usarlo
- cómo verificarlo
- qué límites de seguridad/coste tiene

### 3. Promoción al Foundation
Si la práctica es portable, clara y útil para más de un agente, se añade al Foundation:
- documento core si es una doctrina nueva
- actualización de docs existentes si encaja en una sección actual
- `CHANGELOG.md` con versión/fecha
- `README.md` si añade una pieza estructural nueva

### 4. Consumo por otros agentes
Otros agentes no reciben una receta rígida. Leen el Foundation actualizado y hacen su adaptación local:
- `AGENTS.md` local
- memoria local
- skills locales
- scripts locales
- routing local

La adaptación debe respetar identidad, usuario, permisos, herramientas y privacidad de ese agente.

## Regla de separación

### Vive en Foundation
- principios reutilizables
- patrones operativos generales
- criterios de promoción/verificación
- plantillas neutrales
- changelog de doctrina

### Vive en cada agente
- identidad y tono propios
- memoria privada
- preferencias de su usuario
- credenciales/herramientas/hosts
- rutas, topics, destinatarios
- reglas locales de `AGENTS.md`

## Patrón “beber de la fuente”
Cuando un agente quiera actualizarse desde Foundation:

```bash
# 1. Ver qué versión/doctrina tiene
sed -n '1,40p' docs/agent-foundation/CHANGELOG.md

# 2. Leer índice y cambios
sed -n '1,120p' docs/agent-foundation/README.md
sed -n '1,80p' docs/agent-foundation/CHANGELOG.md

# 3. Leer docs nuevas o relevantes
# Ejemplo para learning loop:
sed -n '1,220p' docs/agent-foundation/LEARNING_LOOP.md

# 4. Adaptar localmente solo lo que aplique
# No copiar memoria privada ni reglas específicas de otro agente.
```

## Ejemplo: Learning Loop v1.7.0
El patrón `learning-loop` entra al Foundation como doctrina reusable:
- `.learnings/` como inbox crudo
- promoción controlada a memoria/skills/scripts/docs
- coste mínimo, sin reflexión LLM rutinaria
- separación entre learning-loop como entrada y skillify como posible salida

Cada agente decide si lo materializa como:
- solo regla en `AGENTS.md`,
- `.learnings/` + reglas de memoria,
- skill local completa,
- helper determinista,
- o una combinación proporcional a su madurez.

## Anti-patrones
- crear recetas por agente dentro del Foundation cuando basta un patrón general
- copiar memoria privada entre agentes
- hacer que un agente mantenedor aplique cambios locales en otros agentes cuando el objetivo es que ellos lean/adapten
- promover prácticas al Foundation sin prueba real
- convertir el Foundation en un dump de hacks locales

## Resultado esperado
El agente mantenedor actúa como jardinero del Foundation: destila aprendizajes reales al repo común. Los demás agentes leen ese repo actualizado y adaptan desde ahí, manteniendo casas separadas pero doctrina compartida.
