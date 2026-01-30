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

## PASO 3: Verificacion
Ejecuta:
- git status (para ver cambios pendientes)
- /cost (para mostrar costo de sesion)

## PASO 4: Preguntar sobre Commit
Si hay cambios, preguntar:
"Quieres que haga commit de los cambios? Describe brevemente que incluir."

## PASO 5: Resumen Final
Mostrar resumen estructurado:
- Fecha
- Costo de sesion
- Lo logrado
- Lo pendiente
- Proximos pasos sugeridos

## PASO 6: Guardar Sesion
Si el trabajo no termino, sugerir: /rename serie-a-junta
