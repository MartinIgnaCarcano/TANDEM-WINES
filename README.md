# TANDEM-WINES

Sitio institucional de **Tándem Wines**, un proyecto boutique de vinos del Este Mendocino. Es una página estática (HTML, CSS y JavaScript sin dependencias ni build) que presenta la historia de la bodega, su terroir, los tres vinos de la colección y los puntos de venta y contacto.

## Estructura

```
.
├── index.html              # Página principal (estilos y scripts incluidos en el archivo)
├── fichas-tecnicas/        # Una ficha técnica por vino
│   ├── hanami.html
│   ├── ieneko.html
│   └── origami.html
├── assets/img/
│   ├── botellas/           # Botellas de cada vino (PNG con transparencia)
│   ├── fondos/             # Ilustraciones de la bodega usadas de fondo
│   ├── logo-tandem-wines.png
│   └── logo-link.png       # Favicon
└── vercel.json             # Configuración de deploy
```

## Secciones de la página

1. **Intro**: logo e invitación a recorrer el sitio.
2. **Nuestra historia**: el origen de Tándem y el manifiesto "Vinos de Sed".
3. **Origen · Terroir**: región, suelo y clima, con un mapa interactivo de Mendoza que marca los viñedos.
4. **Colección**: los tres vinos (**Hanami**, **Ieneko** y **Origami**) en pestañas. Cada uno tiene su color, su botella y un enlace a su ficha técnica.
5. **Cobertura y contacto**: provincias con presencia, mapa interactivo de Argentina, mail y WhatsApp.

La paleta del sitio sale de los colores de las tres botellas y se define como variables CSS en `:root` (`--hanami`, `--neko`, `--origami`).

## Desktop y mobile

- **Desktop (más de 900px de ancho):** cada sección ocupa la pantalla completa y se pasa de una a otra con la rueda del mouse, las flechas del teclado o los indicadores de abajo, con una transición diagonal.
- **Mobile y tablets (hasta 900px):** las secciones se apilan y se recorren con scroll vertical. Cada una aparece con una animación al entrar en pantalla, y la barra superior muestra el avance. Las pestañas de los vinos se ubican en horizontal sobre la botella. Para simplificar la vista, se ocultan la tarjeta del logo en "Nuestra historia" y el mapa de Mendoza en "Origen".

Todos los estilos mobile están en el bloque `@media (max-width: 900px)` de `index.html`.

## Correr localmente

No requiere instalación. Se puede abrir `index.html` directamente en el navegador o levantar un servidor estático:

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

## Deploy

El sitio se publica en [Vercel](https://vercel.com). `vercel.json` activa las URLs limpias (sin `.html`) y define una caché de 7 días para los archivos de `assets/`.
