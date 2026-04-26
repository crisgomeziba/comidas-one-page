# comidas-one-page

One page para GitHub Pages que muestra en pantalla completa qué comer según la hora del día.

## Cómo funciona

- Detecta si es **desayuno** (6-11h), **almuerzo** (11-16h) o **cena** (18-23h)
- Elige una comida de la lista de forma estable durante todo el día (si recargás, sale la misma)
- Muestra la imagen de fondo a pantalla completa con el nombre de la comida
- Fuera de horario muestra "¡A descansar!"

## Estructura

```
comidas-one-page/
├── index.html
└── img/
    ├── desayuno/   ← imágenes de desayuno
    ├── almuerzo/   ← imágenes de almuerzo
    └── cena/       ← imágenes de cena
```

## Agregar comidas

1. Copiá la imagen a la carpeta correspondiente dentro de `img/`
2. Agregá una línea en `OPCIONES` dentro del `<script>` en `index.html`:

```js
{ nombre: "Nombre del plato", imagen: "img/almuerzo/nombre-archivo.png" }
```

## Imágenes actuales

### Almuerzo
- Carne con puré — `img/almuerzo/carne-con-pure.png`
- Fideos con salsa — `img/almuerzo/fideos-con-salsa.png`
- Pollo con arroz — `img/almuerzo/pollo-con-arroz.png`
- Porotos — `img/almuerzo/porotos.png`
- Lentejas — `img/almuerzo/lentejas.png`
- Burritos — `img/almuerzo/burritos.png`
- Estofado de carne — `img/almuerzo/estofado-de-carne.png`
- Reineta con puré — `img/almuerzo/reineta-con-pure.png`
- Salmón a la mantequilla con arroz — `img/almuerzo/salmon-a-la-mantequilla-con-arroz.png`
- Chuleta con puré — `img/almuerzo/chuleta-con-pure.png`

### Desayuno
- Pan con palta — `img/desayuno/pan-con-palta-bebida-caliente.png`
- Quesadillas y huevo — `img/desayuno/quesadillas-huevo.png`
- Yogurt y fruta — `img/desayuno/yogurt-y-fruta.png`
- Pan con huevo y tomate — `img/desayuno/pan-con-huevo-y-tomate.png`
- Pan con queso fresco — `img/desayuno/pan-con-queso-fresco.png`
- Pan con ricotta y salame — `img/desayuno/pan-con-ricotta-y-salame.png`
- Tostadas con mantequilla — `img/desayuno/tostadas-con-mantequilla.png`

### Cena
- Pan con palta — `img/cena/pan-con-palta-bebida-caliente.png`
- Galletas con atún — `img/cena/galletas-con-atun.png`
- Quesadillas y huevo — `img/cena/quesadillas-huevo.png`
- Pan con huevo y tomate — `img/cena/pan-con-huevo-y-tomate.png`
- Pan con queso fresco — `img/cena/pan-con-queso-fresco.png`
- Pan con ricotta y salame — `img/cena/pan-con-ricotta-y-salame.png`
- Tostadas con mantequilla — `img/cena/tostadas-con-mantequilla.png`

## Fijar menú por día

En `index.html`, editá `MENU_SEMANAL` para asignar comidas fijas a días específicos:

```js
const MENU_SEMANAL = {
  1: { // Lunes
    almuerzo: { nombre: "Milanesa", imagen: "img/almuerzo/milanesa.png" },
  },
};
```

## Deploy

GitHub Pages → Settings → Pages → Branch: `main` / Folder: `/ (root)`
