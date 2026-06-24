# Tanto Corazón · Catálogo de floristería

Sitio estático de una sola página para **Tanto Corazón**, floristería artesanal en San Luis Potosí, México. Catálogo de ramos y arreglos, políticas de entrega, costos de envío y contacto por WhatsApp e Instagram.

## Estructura

```
index.html     Página (plantilla Design Canvas con <x-dc> + bindings {{ }})
support.js     Runtime que renderiza la plantilla (carga React 18 desde unpkg)
assets/        Imágenes del catálogo, logo y mapa de envíos
```

El contenido del catálogo (productos, precios, políticas) vive embebido en el
bloque `<script type="text/x-dc">` al final de `index.html`. Edítalo ahí.

## Desarrollo local

Es 100% estático; sírvelo con cualquier servidor:

```bash
npx serve .
# o
python3 -m http.server 8000
```

Luego abre `http://localhost:8000`. Requiere conexión a internet (React y las
fuentes se cargan desde CDN).

## Deploy

Desplegado en Vercel como sitio estático (sin build). Importa el repo en
[vercel.com](https://vercel.com) — framework preset **Other**, sin comando de build.

## Configuración rápida

En el `<script type="text/x-dc">` de `index.html`:

- `phone` — número de WhatsApp (formato internacional sin `+`).
- `instagram` — URL del perfil.
- `showPrices` (prop) — mostrar/ocultar precios.
- `accentColor` (prop) — color de acento.
- `raw[]` — los productos del catálogo.
- `policies[]` — las políticas de entrega.
