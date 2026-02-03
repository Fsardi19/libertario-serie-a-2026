# Guia de Dashboards - Libertario Coffee

**Ultima actualizacion:** 2026-02-02
**Proposito:** Referencia para crear dashboards HTML consistentes y responsive

---

## Colores de Marca

```css
:root {
    --libertario-blue: #182b55;      /* Azul principal */
    --libertario-gold: #c9a227;      /* Dorado/Oro */
    --libertario-cream: #f5f1eb;     /* Crema fondo */
    --libertario-light-blue: #2a4a8a; /* Azul claro */
    --success-green: #28a745;
    --warning-orange: #fd7e14;
    --danger-red: #dc3545;
}
```

## Colores por Pais

```css
--colombia: #FFD700;   /* Amarillo */
--mexico: #006847;     /* Verde */
--costarica: #002b7f;  /* Azul */
--india: #FF9933;      /* Naranja */
--chile: #D52B1E;      /* Rojo */
```

## Banderas (Emojis)

Usar emojis directamente (no HTML entities):
- Colombia: 🇨🇴
- Mexico: 🇲🇽
- Costa Rica: 🇨🇷
- India: 🇮🇳
- Chile: 🇨🇱
- USA: 🇺🇸

---

## Estructura Base HTML

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Libertario Coffee - [Titulo]</title>
    <style>
        /* Variables CSS */
        /* Reset basico */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }

        /* Estilos principales */
        /* Media queries al final */
    </style>
</head>
<body>
    <div class="header">...</div>
    <div class="container">...</div>
    <div class="footer">...</div>
</body>
</html>
```

---

## Componentes Reutilizables

### 1. Header con Gradiente

```css
.header {
    background: linear-gradient(135deg, var(--libertario-blue) 0%, var(--libertario-light-blue) 100%);
    color: white;
    padding: 40px 60px;
    position: relative;
    overflow: hidden;
}

.header::before {
    content: '';
    position: absolute;
    top: -50%;
    right: -10%;
    width: 400px;
    height: 400px;
    background: var(--libertario-gold);
    opacity: 0.1;
    border-radius: 50%;
}
```

### 2. Summary Cards

```css
.summary-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

.summary-card {
    background: white;
    border-radius: 16px;
    padding: 24px;
    box-shadow: 0 4px 20px rgba(24, 43, 85, 0.08);
    border-left: 5px solid var(--libertario-gold);
}

.summary-card.highlight {
    background: var(--libertario-blue);
}
.summary-card.highlight .value {
    color: var(--libertario-gold);
}
```

### 3. Progress Bars

```css
.progress-bar {
    height: 10px;
    background: #e9ecef;
    border-radius: 5px;
    overflow: hidden;
}

.progress-fill {
    height: 100%;
    border-radius: 5px;
    transition: width 0.5s ease;
}

.progress-fill.high { background: linear-gradient(90deg, #28a745, #20c997); }
.progress-fill.medium { background: linear-gradient(90deg, #fd7e14, #ffc107); }
.progress-fill.low { background: linear-gradient(90deg, #dc3545, #fd7e14); }
```

### 4. Pipeline Cards

```css
.pipeline-card {
    background: white;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 4px 20px rgba(24, 43, 85, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.pipeline-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 30px rgba(24, 43, 85, 0.15);
}

.card-header.colombia { background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%); }
.card-header.mexico { background: linear-gradient(135deg, #006847 0%, #00a86b 100%); }
/* etc... */
```

### 5. Tablas

```css
.projection-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    background: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 20px rgba(24, 43, 85, 0.1);
}

.projection-table th {
    background: var(--libertario-blue);
    color: white;
    padding: 16px;
}

.projection-table tr.total-row {
    background: var(--libertario-blue);
    color: white;
}
```

### 6. Galeria de Fotos

```css
.gallery-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
}

.gallery-item {
    position: relative;
    border-radius: 12px;
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s ease;
}

.gallery-item:hover { transform: scale(1.03); }

.gallery-item img {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.gallery-item .overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(transparent, rgba(24, 43, 85, 0.9));
    padding: 20px 16px 16px;
    color: white;
}
```

---

## Media Queries - RESPONSIVE

### Breakpoints

| Breakpoint | Dispositivo |
|------------|-------------|
| 1200px | Tablet grande / Desktop pequeño |
| 768px | Tablet |
| 480px | Movil |

### Template Responsive Completo

```css
/* Tablet grande */
@media (max-width: 1200px) {
    .pipeline-grid { grid-template-columns: repeat(2, 1fr); }
    .gallery-grid { grid-template-columns: repeat(3, 1fr); }
    .container { padding: 30px; }
}

/* Tablet */
@media (max-width: 768px) {
    .header { padding: 30px 20px; }
    .header-content { flex-direction: column; text-align: center; gap: 20px; }

    .summary-grid { grid-template-columns: repeat(2, 1fr); gap: 12px; }
    .summary-card .value { font-size: 1.6rem; }

    .pipeline-grid { grid-template-columns: 1fr; }

    .gallery-grid { grid-template-columns: repeat(2, 1fr); }
    .gallery-item img { height: 150px; }

    /* Tabla y timeline con scroll */
    .projection-table { font-size: 0.85rem; }
    .timeline { min-width: 600px; }
}

/* Movil */
@media (max-width: 480px) {
    .header { padding: 20px 15px; }
    .logo-section h1 { font-size: 1.5rem; }

    .container { padding: 15px 12px; }

    .summary-grid { grid-template-columns: 1fr; }
    .summary-card .value { font-size: 1.8rem; }

    .section-header .icon { width: 36px; height: 36px; }
    .section-header h2 { font-size: 1rem; }

    .gallery-grid { grid-template-columns: 1fr 1fr; gap: 10px; }
    .gallery-item img { height: 120px; }

    /* Timeline compacto */
    .timeline-container { padding: 10px; }
    .timeline { min-width: 400px; }
    .month-label { font-size: 0.65rem; }
    .timeline-item { font-size: 0.55rem; padding: 4px 6px; }
    .month-revenue .value { font-size: 0.75rem; }

    /* Tabla compacta */
    .projection-table {
        font-size: 0.65rem;
        display: block;
        overflow-x: auto;
    }
    .projection-table th { font-size: 0.6rem; padding: 8px 5px; }
    .projection-table td { padding: 6px 5px; }
}
```

---

## Mejores Practicas

1. **Viewport meta tag** - Siempre incluir:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

2. **Imagenes responsive** - Usar `object-fit: cover` y altura fija

3. **Tablas en movil** - Usar `display: block; overflow-x: auto;`

4. **Timeline en movil** - Scroll horizontal con `min-width`

5. **Fuentes** - Reducir 30-40% en movil

6. **Padding** - Reducir a la mitad en movil

7. **Grids** - De 4 columnas a 1 columna progresivamente

---

## Archivos de Referencia

| Dashboard | Ubicacion |
|-----------|-----------|
| Pipeline Tiendas | `output/presentacion/PIPELINE_TIENDAS_FEBRERO_2026.html` |
| Embudo Inversionistas | `output/presentacion/DASHBOARD_EMBUDO_INVERSIONISTAS.html` |
| Informe Junta | `output/presentacion/INFORME_JUNTA_SERIE_A_2026_v2.html` |

---

## GitHub Pages

**URL:** https://fsardi19.github.io/libertario-serie-a-2026/

**Configuracion:**
- Carpeta: `/docs`
- Deployment: GitHub Actions
- Workflow: `.github/workflows/static.yml`

Para publicar cambios:
```bash
# Copiar HTML a docs/
cp output/presentacion/ARCHIVO.html docs/index.html

# Copiar imagenes
cp -r fotos_obra docs/

# Commit y push
git add -A && git commit -m "Actualizar dashboard" && git push origin main
```
