# Start Here

## Objetivo
Aplicar `Agent Foundation` a un agente de OpenClaw justo después de su bootstrap nativo.

## Cuándo
Primero, dejar que el agente nazca solo:
- OpenClaw instalado y al menos un modelo funcionando
- el usuario se presenta y el agente completa su rutina nativa de bootstrap (identidad, usuario, workspace)

Justo después, aplicar el Foundation: cuanto antes entren estas reglas, menos hábitos hay que corregir.

## Paso 1 — Leer la base
- `README.md`
- `CORE_PRINCIPLES.md`
- `VERIFICATION.md`

## Paso 2 — Sembrar reglas en `AGENTS.md`
Partir de `templates/AGENTS_TEMPLATE.md` y fusionarlo con el `AGENTS.md` existente del agente:
- conservar identidad, tono y reglas propias que ya tenga
- añadir las reglas operativas que falten

## Paso 3 — Aterrizar en el entorno real
Con `MODEL_ROUTING.md`, `SUBAGENT_POLICY.md` y `ROUTING_AND_ISOLATION.md`, dejar escrito en archivos del workspace:
- qué modelos hay de verdad y cuáles cubre el plan real
- qué rol cumple cada modelo y cuál es el fallback
- cuándo delegar y en qué runtime
- cómo se organizan canales/topics y dónde llegan las alertas

Partir de `templates/ROUTING_TEMPLATE.md` si ayuda.

## Paso 4 — Mantenimiento del host
Si el agente vive en un servidor siempre encendido, aplicar `HOUSEKEEPING.md`:
- watchdog del gateway que distinga update/reboot de caída real
- watcher barato de updates del host
- alertas solo por cambio o problema
- restore sencillo y probado

Si vive en un equipo personal, aplicar solo lo que tenga sentido allí.

## Paso 5 — Cerrar el ciclo de aprendizaje
Usar `ERROR_LEARNING.md` e `IMPROVEMENT.md` para que errores e ideas externas acaben en reglas, scripts o tests, no en chat.

## Checklist inicial
- ¿consulta historia local antes que APIs vivas?
- ¿su routing de modelos está escrito y probado?
- ¿verifica antes de declarar éxito?
- ¿sus reglas operativas viven en archivos?
- ¿abre panorama 360 antes de cambios importantes?
- ¿sus planes describen el comportamiento deseado además de los pasos?
- ¿distingue subagente aislado de sesión persistente?
- si es un servidor: ¿un update o reboot puede dejarlo colgado sin aviso?

## Actualizarse
Cuando el Foundation cambie:
1. leer `CHANGELOG.md`
2. leer los documentos nuevos o modificados
3. decidir qué aplica a su entorno
4. adaptar sus archivos locales (`AGENTS.md`, skills, scripts)

## Regla
Lo que dejó el bootstrap (identidad, tono, datos del usuario) se respeta. El Foundation aporta doctrina general; identidad, memoria, credenciales, hosts, rutas y canales son propios de cada agente.
