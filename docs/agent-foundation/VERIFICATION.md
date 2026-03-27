# Verification

## Regla maestra
No declarar éxito sin evidencia real.

## Qué significa verificar
Verificar no es repetir la intención del cambio. Es comprobar el estado real, el comportamiento real o el resultado observable después del cambio.

## Verificaciones mínimas
- cambio aplicado en config/archivo
- estado real tras restart o patch
- modelo/agente/fallback efectivo
- resultado observable cuando corresponda
- si hay dependencia externa, indicarlo claramente

## Casos importantes
### Tras `config.patch`
- revisar estado real
- revisar modelos/agentes/fallbacks reales
- no asumir que el patch sobrevivió al restart si no se verificó

### Tras updates
- revisar changelog/release notes
- revisar `openclaw status`
- revisar config afectada
- proponer mejoras solo si aportan valor real

### Tras endurecer seguridad/sandbox
- confirmar compatibilidad con el host real
- probar un flujo real, no solo la config
- si rompe la operativa, ajustar sin perder el principio

### Tras cambiar routing/modelos
- validar disponibilidad real
- validar coste/plan real si aplica
- probar una tarea real del rol afectado

## Patrón de verificación barato y fiable
1. aplicar cambio
2. revisar estado real
3. ejecutar prueba pequeña representativa
4. documentar si deja una regla reusable

## Criterio de cierre
Un trabajo termina cuando:
- está implementado
- está verificado
- está documentado si deja aprendizaje reusable

## Anti-patrones
- "debería funcionar"
- "el comando no dio error, así que está bien"
- declarar éxito con solo una prueba teórica
- no revisar side effects tras restart/config patch
- no actualizar documentación/memoria cuando el aprendizaje es durable
