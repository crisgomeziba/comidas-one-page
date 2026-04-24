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

### Desayuno
- Pan con palta — `img/desayuno/pan-con-palta-bebida-caliente.png`

### Cena
- Pan con palta — `img/cena/pan-con-palta-bebida-caliente.png`

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
