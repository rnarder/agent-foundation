# Error Learning

## Objetivo
Convertir cada error importante en prevención duradera.

## Regla maestra
Un error no termina cuando se arregla. Termina cuando deja una mejora reusable en el sistema.

## Formato mínimo
- Qué pasó
- Por qué pasó
- Qué se cambió
- Qué regla preventiva queda

## Cuándo registrar
- errores repetibles
- regresiones
- malos supuestos
- routing incorrecto
- coste inesperado
- fallos de aislamiento o verificación
- cambios que parecían correctos en teoría y fallaron en el host real

## Tipos de aprendizaje que suelen valer oro
### 1. Supuesto falso
Ejemplo abstracto: asumir que un catálogo de modelos equivale a disponibilidad real.

### 2. Verificación insuficiente
Ejemplo abstracto: aplicar config y no comprobar el estado real tras restart.

### 3. Aislamiento mal entendido
Ejemplo abstracto: asumir que la organización visual separa memoria o ejecución real.

### 4. Complejidad que se volvió en contra
Ejemplo abstracto: endurecer seguridad de una forma que rompe la operativa real del host.

## Cómo promover el aprendizaje
- si la lección es de comportamiento → `lessons.md` o equivalente
- si es estructural/reusable → docs core del framework
- si es local/operativa → documentación del host/agente concreto

## Anti-patrones
- arreglar rápido y olvidar
- culpar al modelo sin revisar sistema y contexto
- documentar solo el síntoma, no la causa raíz
- repetir el mismo error porque la regla nunca quedó escrita
