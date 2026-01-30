# Protocolo de Cierre de Sesion

Ejecuta el siguiente protocolo de cierre:

## PASO 1: Documentar la Sesion
Actualiza .claude/SESSION_LOG.md agregando una nueva entrada con:
- Fecha
- Objetivo de la sesion
- Lo que se completo
- Archivos modificados/creados
- Lo que quedo pendiente
- Notas importantes
- Prioridades para proxima sesion

## PASO 2: Actualizar Progreso
Actualiza .claude/PROGRESO.md con el estado actual de cada componente.

## PASO 3: Sincronizar con GitHub
Ejecuta los siguientes comandos para guardar en GitHub:
```bash
cd "/Users/felipesardi/Desktop/EL GREEN HUB/COFFEE SHOPS/AI STRATEGY/SERIE A 2026"
git add -A
git commit -m "Cierre sesion [FECHA] - [RESUMEN BREVE]

- [Lista de cambios principales]

Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>"
git push origin main
```

## PASO 4: Verificacion
Confirma que el push fue exitoso mostrando:
- git status
- URL del repositorio: https://github.com/Fsardi19/libertario-serie-a-2026

## PASO 5: Resumen Final
Mostrar resumen estructurado:
- Fecha
- Lo logrado
- Lo pendiente
- Proximos pasos sugeridos
- Confirmacion de sync con GitHub
