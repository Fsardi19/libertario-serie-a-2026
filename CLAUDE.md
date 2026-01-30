# SERIE A 2026 - Libertario Coffee

## PROTOCOLO DE INICIO DE SESION

**AL INICIAR CUALQUIER SESION, CLAUDE CODE DEBE:**

1. Leer estos archivos EN ORDEN:
   - Este CLAUDE.md
   - .claude/SESSION_LOG.md (si existe)
   - .claude/PROGRESO.md (si existe)

2. Ejecutar diagnostico:
   - ls -la
   - ls -la .claude/
   - git status

3. Dar resumen de:
   - Estado del proyecto
   - Ultima sesion (que se hizo)
   - Que quedo pendiente
   - Sugerencias para esta sesion

4. PREGUNTAR: "Que quieres lograr en esta sesion?"

**NO empezar a trabajar hasta que el usuario confirme el objetivo.**

---

## Estructura del Proyecto

```
SERIE A 2026/
├── CLAUDE.md                    ← Este archivo
├── .claude/
│   ├── commands/
│   │   ├── start.md             ← Comando /project:start
│   │   └── close.md             ← Comando /project:close
│   ├── SESSION_LOG.md           ← Historial de sesiones
│   └── PROGRESO.md              ← Estado del trabajo
├── output/
│   ├── datos/
│   ├── anexos/
│   └── presentacion/
└── [archivos fuente]
```

---

## Contexto del Proyecto

**Proyecto:** Preparacion Serie A 2026 para Libertario Coffee
**Objetivo:** Informe para Junta Directiva

**3 Aspectos a cubrir:**
1. Negociacion con Roman Irrure
2. Propuesta One To One Bank (Juan Emilio Posada)
3. Analisis de multiplos y valoracion

**Archivos fuente:**
- Oferta Roman Irrure.rtfd/ → Emails negociacion
- Ono to One Bank .rtfd/ → Correspondencia banca
- ONEtoONE_WhoWeAre_2025-3 (5) 2.pptx → Presentacion banca
- Libertario & Futura - Investment Deck 2025 (Oct - 2025).pdf → Deck principal
- Analisis de multiplos de valoracion...pdf → Benchmarks
- Valoraciones comparables...pdf → Comparables
- Blue Tokai.xlsx, Third Wave Coffee.xlsx → Comparables India
- Watch House financials.pdf → Comparable UK

---

## Reglas de Operacion

### SIEMPRE:
- Citar fuente de cada dato (archivo, pagina)
- Usar Python para extraer informacion
- Generar JSON intermedio para trazabilidad
- Pedir confirmacion antes de cambios grandes
- Usar /compact cada 10-15 mensajes
- Documentar en SESSION_LOG.md al cerrar

### NUNCA:
- Inventar datos financieros o multiplos
- Asumir terminos no documentados
- Calcular mentalmente (siempre codigo)
- Modificar archivos fuente
- Cerrar sin documentar

---

## Comandos de Sesion

| Comando | Funcion |
|---------|---------|
| /project:start | Ejecutar protocolo de apertura |
| /project:close | Ejecutar protocolo de cierre |
| /compact | Comprimir historial |
| /context | Ver tokens usados |
| /cost | Ver costo de sesion |
