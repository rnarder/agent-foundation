# New Agent Adoption

## Objetivo
Definir cómo usar `Agent Foundation` para crear un agente nuevo sin copiar basura contextual ni perder las prácticas maduras.

## Momento de adopción
Este framework entra en juego **después** del estado inicial limpio de OpenClaw.

Precondiciones recomendadas:
- OpenClaw ya instalado
- al menos un modelo ya configurado y funcional
- workspace ya creado
- bootstrap inicial ya completado
- primer intercambio usuario/agente ya ocurrido

A partir de ahí, el agente puede leer `Agent Foundation` y adoptarlo como base operativa.

## Orden recomendado
### 1. Partir del estado limpio existente
No reinstalar OpenClaw ni rehacer onboarding si ya existe un agente funcional mínimo.

### 2. Instanciar base
Crear o preparar:
- `AGENTS.md`
- `SOUL.md`
- `USER.md`
- `MEMORY.md`
- `memory/`
- docs/routing locales si aplica

### 3. Copiar solo la capa reusable
Usar desde `Agent Foundation`:
- principios core
- sistema de memoria
- routing/model policy reusable
- política de subagentes
- verificación
- housekeeping
- error learning
- plantillas

### 4. Personalizar la capa local
Definir:
- identidad propia del agente
- a quién ayuda
- tono
- límites
- objetivos
- temas y workflows propios

### 5. Configurar entorno
Definir:
- canales/topics
- tools disponibles
- hosts/cron/workflows
- límites operativos reales

### 6. Validar nacimiento del agente
Checklist mínimo:
- ¿tiene identidad propia?
- ¿tiene memoria separada?
- ¿no arrastra datos privados de otro agente?
- ¿sus reglas duraderas ya están en archivos?
- ¿su routing está claro?
- ¿su entorno real fue probado?

## Qué nunca copiar tal cual
- memoria privada de otro agente
- datos personales del usuario de otro agente
- rutas/hosts/tokens sensibles
- topics/routing específicos de otro entorno
- workarounds locales sin validar

## Qué sí conviene copiar
- estructura mental y operativa
- disciplina de costes
- verificación
- aprendizaje de errores
- patrones de housekeeping
- límites de delegación y aislamiento

## Regla
Crear un agente nuevo no es clonar uno viejo. Es tomar un agente recién nacido y funcional, aplicarle una base madura, y luego personalizar con intención.
