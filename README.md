# MapuTru Repostera — Página de productos

Sitio estático (HTML/CSS/JS puro, sin build) con el catálogo de MapuTru: línea saludable, tortas completas, postres individuales, sánduches, opción empresarial, promociones, políticas y pedidos por WhatsApp.

## Estructura

```
index.html      → toda la página (HTML + CSS + JS en un solo archivo)
images/         → logo, íconos y fotos de producto
vercel.json     → cache headers para las imágenes
```

No hay dependencias ni proceso de build: es un sitio 100% estático.

## Subir a GitHub

Desde esta carpeta:

```bash
git init
git add .
git commit -m "Sitio MapuTru Repostera"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/NOMBRE_DEL_REPO.git
git push -u origin main
```

(Crea antes el repo vacío en GitHub, sin README ni .gitignore, para evitar conflictos al hacer push.)

## Desplegar en Vercel

**Opción A — desde la web (más fácil):**
1. Entra a [vercel.com](https://vercel.com) e inicia sesión con tu cuenta de GitHub.
2. "Add New" → "Project" → selecciona el repo que acabas de subir.
3. Framework Preset: elige **"Other"** (es un sitio estático, no necesita build command).
4. Deploy. En un par de minutos tendrás una URL tipo `maputru.vercel.app`.

**Opción B — desde la terminal:**
```bash
npm install -g vercel
vercel login
vercel --prod
```

## Dominio propio

Una vez desplegado, en el panel de Vercel ve a **Settings → Domains** y agrega tu dominio (por ejemplo `maputru.com` o `maputru.co`) si ya tienes uno comprado. Vercel te da los registros DNS que debes apuntar.

## Actualizar el sitio más adelante

Cualquier cambio que hagas en `index.html` o en `images/`, simplemente:

```bash
git add .
git commit -m "Actualización de productos"
git push
```

Vercel vuelve a desplegar automáticamente con cada push a `main`.

## Notas

- El número de WhatsApp está harcodeado en el HTML (`WA_NUMBER` dentro del `<script>` al final del archivo). Si cambia, se actualiza ahí.
- Las fotos que dicen "Foto próximamente" (pie de limón, pie de limón saludable, cheesecake de arándanos, pavlovas) se reemplazan agregando el archivo a `images/` y actualizando el `<img>` correspondiente en `index.html`.
