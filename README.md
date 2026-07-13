# Planificador de Pilares — Solares Método

Demo web de una sola pantalla para planificar el contenido de Instagram y LinkedIn
según el **pilar de cada día** de la semana. Parte de la marca **Imagen con Propósito ·
Solares Método** ([@soymayasolares](https://instagram.com/soymayasolares)).

## Qué hace
- **Selector de día** (lunes a sábado; domingo descansa).
- Al elegir el día, muestra **el pilar que le corresponde** y su paleta de color:
  - **Lunes** — Presencia que Impacta *(navy)*
  - **Martes** — Autoridad que se Construye *(vino)*
  - **Miércoles** — Tu Voz, Tu Poder *(navy)*
  - **Jueves** — El Entorno que te Representa *(vino)*
  - **Viernes** — Testimonios *(navy)*
  - **Sábado** — Contenido especial *(alto contraste blanco/negro)*
- Campo de **tema del día** y **checklist de formatos** a crear
  (lunes–viernes: Historia, Post sencillo, Guion, Caption, Carrusel · sábado: Post sencillo, Caption).
- Todo se **guarda en el navegador** (`localStorage`): al recargar, no se pierde nada.

## Tecnología
Un solo archivo **`index.html`** autocontenido (HTML + CSS + JS embebidos).
Sin backend, sin base de datos externa, sin instalación.
Tipografías: Playfair Display · Montserrat · Great Vibes (Google Fonts).

## Ver en local
Doble clic en `index.html`, o servir la carpeta con cualquier servidor estático.

## Archivos que se publican
- `index.html` — la app.
- `img/` — las fotos de cada día (`lunes.jpg`, `martes.jpg`, `miercoles.jpg`,
  `jueves.jpg`, `viernes.jpg`, `sabado.jpg`), optimizadas para web.
- `README.md` — este archivo.

*(El documento `.docx` de instrucciones no se publica: está excluido en `.gitignore`.)*

## Publicar en Vercel
1. Sube esta carpeta a un repositorio de **GitHub** (incluye `index.html` **y** la carpeta `img/`).
2. En [vercel.com](https://vercel.com) → **Add New → Project** → importa el repositorio.
3. Framework Preset: **Other** (no requiere build). Deja todo por defecto y **Deploy**.
4. Vercel sirve `index.html` con sus imágenes en la URL pública que te da.
