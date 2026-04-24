# Contexto para agente — comidas-one-page

## Qué es este proyecto

One page estática hosteada en GitHub Pages (`https://crisgomeziba.github.io/comidas-one-page/`).
Muestra en pantalla completa (sin scroll) qué comer según la hora del día: desayuno, almuerzo o cena.
Todo es un único archivo `index.html` + imágenes locales.

## Estructura del repo

```
comidas-one-page/
├── index.html        ← toda la lógica y estilos están acá
├── agents.md         ← este archivo
├── README.md         ← documentación del proyecto
└── img/
    ├── desayuno/     ← imágenes de desayuno
    ├── almuerzo/     ← imágenes de almuerzo
    └── cena/         ← imágenes de cena
```

## Cómo funciona la lógica

- **Horarios** definidos en `HORARIOS` (desayuno 6-11h, almuerzo 11-16h, cena 18-23h)
- **Selección**: seed basado en la fecha → misma comida todo el día; cambia al día siguiente
- **Roll**: botón en esquina inferior derecha cicla entre opciones; offset guardado en `localStorage` por día y tipo de comida
- **Menú fijo**: `MENU_SEMANAL` permite fijar comidas por día de la semana (actualmente vacío)
- Fuera de horario muestra "¡A descansar!" con fondo oscuro y oculta el botón roll

## Imágenes actuales

### Desayuno (7)
- Pan con palta — `img/desayuno/pan-con-palta-bebida-caliente.png`
- Quesadillas y huevo — `img/desayuno/quesadillas-huevo.png`
- Yogurt y fruta — `img/desayuno/yogurt-y-fruta.png`
- Pan con huevo y tomate — `img/desayuno/pan-con-huevo-y-tomate.png`
- Pan con queso fresco — `img/desayuno/pan-con-queso-fresco.png`
- Pan con ricotta y salame — `img/desayuno/pan-con-ricotta-y-salame.png`
- Tostadas con mantequilla — `img/desayuno/tostadas-con-mantequilla.png`

### Almuerzo (9)
- Carne con puré — `img/almuerzo/carne-con-pure.png`
- Fideos con salsa — `img/almuerzo/fideos-con-salsa.png`
- Pollo con arroz — `img/almuerzo/pollo-con-arroz.png`
- Porotos — `img/almuerzo/porotos.png`
- Lentejas — `img/almuerzo/lentejas.png`
- Burritos — `img/almuerzo/burritos.png`
- Estofado de carne — `img/almuerzo/estofado-de-carne.png`
- Reineta con puré — `img/almuerzo/reineta-con-pure.png`
- Salmón a la mantequilla con arroz — `img/almuerzo/salmon-a-la-mantequilla-con-arroz.png`

### Cena (7)
- Pan con palta — `img/cena/pan-con-palta-bebida-caliente.png`
- Galletas con atún — `img/cena/galletas-con-atun.png`
- Quesadillas y huevo — `img/cena/quesadillas-huevo.png`
- Pan con huevo y tomate — `img/cena/pan-con-huevo-y-tomate.png`
- Pan con queso fresco — `img/cena/pan-con-queso-fresco.png`
- Pan con ricotta y salame — `img/cena/pan-con-ricotta-y-salame.png`
- Tostadas con mantequilla — `img/cena/tostadas-con-mantequilla.png`

## Workflow habitual

1. Usuario copia imágenes a `img/desayuno/`, `img/almuerzo/` o `img/cena/`
2. Agente detecta imágenes nuevas con `ls` y actualiza `OPCIONES` en `index.html` y la lista en `README.md`
3. Agente hace commit y push a `origin main`

### Convenciones de nombres de archivo
- Minúsculas, palabras separadas por guión (`pollo-con-arroz.png`)
- Formato PNG
- El nombre del archivo se usa directamente como base para el `nombre` en `OPCIONES` (con capitalización apropiada)

## Convenciones de commits

- Mensajes en español
- Formato: acción + qué se agregó/cambió
- Siempre incluir `Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>`
- Un solo commit por sesión de cambios (no uno por imagen)

## Dónde está cada cosa en index.html

| Sección | Línea aprox. | Descripción |
|---|---|---|
| `HORARIOS` | ~107 | Rangos de hora por tipo de comida |
| `MENU_SEMANAL` | ~125 | Menú fijo por día de la semana |
| `OPCIONES` | ~139 | Lista de comidas con nombre e imagen |
| `getRollOffset` / `saveRollOffset` | ~175 | Persistencia del roll en localStorage |
| `getComidaAleatoria` | ~190 | Selección con seed por fecha + offset |
| `render()` | ~198 | Actualiza el DOM |
| Botón roll (HTML) | ~232 | SVG shuffle en esquina inferior derecha |
| Botón roll (CSS) | ~90 | Estilos glassmorphism + animaciones |

## Pendientes / ideas futuras

- Agregar más imágenes de cena
- Completar `MENU_SEMANAL` si se quiere control por día
- Considerar transición animada al hacer roll (fade de imagen)
