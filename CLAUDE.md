# CLAUDE.md — Planificador de Pilares (Solares Método)

Guía del proyecto. Léela antes de hacer cambios.

## Qué es
Una **demo web de una sola pantalla** llamada **"Planificador de Pilares — Solares Método"**.
Sirve para **mostrar a clientas** cómo organizar su contenido de Instagram/LinkedIn según
el **pilar de cada día** de la semana. Es una **demostración**, no una herramienta interna.
Sin backend, sin base de datos, sin login: todo se guarda en el navegador (`localStorage`).

## Estructura de archivos
```
APP CONTENIDO/
├── index.html            # Toda la app (HTML + CSS + JS en un solo archivo autocontenido)
├── img/                  # 6 fotos, una por día: lunes/martes/miercoles/jueves/viernes/sabado.jpg
├── README.md             # Descripción + pasos de publicación
├── CLAUDE.md             # Este archivo
└── App Contenido.docx    # Instrucciones de Maya. NO se publica (fuera de control de versiones)
```
- `index.html` es el único archivo del sitio. No hay build ni dependencias locales.

## Cómo funciona (secciones de la app)
1. **Cabecera:** logo en texto `@soymayasolares` + título "Planificador de Pilares · Solares Método".
2. **Selector de día:** botones **lunes a sábado** (domingo queda fuera). Marca "Hoy" el día actual;
   al abrir, selecciona el día de hoy (o lunes si es domingo).
3. **Panel del día:** foto del día + nombre del pilar + descripción. La **paleta cambia según el día**.
4. **Tema del día:** campo de texto libre.
5. **Formatos a crear (acordeón con editores):** cada formato se despliega y **guarda su contenido**:
   - **Historia** → texto + 1 foto · **Post sencillo** → texto · **Guion** → tabla de reel 18 s
     (4 bloques fijos: Gancho 0–3s, Contexto 3–8s, Desarrollo 8–14s, Cierre 14–18s; columnas
     *Video (acción)* y *Texto*) · **Caption** → texto · **Carrusel** → diapositivas (texto +
     imagen opcional, **máx. 15**).
   - **Sábado** usa checklist reducido: solo **Post sencillo** y **Caption**.
   - Cada formato tiene una casilla "listo" que alimenta la barra de progreso.

## Pilares por día
- Lunes → **Presencia que Impacta** · Martes → **Autoridad que se Construye**
- Miércoles → **Tu Voz, Tu Poder** · Jueves → **El Entorno que te Representa**
- Viernes → **Testimonios** · Sábado → **Contenido especial**

## Decisiones de diseño
- **Un solo archivo** (`index.html`) por simplicidad y para publicar gratis sin instalar nada.
- **Paletas por día** (variables CSS por `[data-dia]`):
  - Lun/Mié/Vie → **Navy** `#0D1B2A` + Gold `#C9A96E` + White `#F5F0E8`
  - Mar/Jue → **Vino/Plum** `#740535` + Gold + White
  - Sáb → **alto contraste blanco/negro** (sin los colores de los otros días)
- **Tipografías (Google Fonts):** Playfair Display (títulos), Montserrat (cuerpo), Great Vibes (acentos).
- **Ilustraciones SVG** por pilar (motivo de sol → "Solares") como respaldo si una foto no carga.
- **Mobile-first / responsive:** en móvil todo pasa a una columna; la tabla del guion se apila.
- **Imágenes:** las fotos del hero se optimizan (~1200 px) y se nombran en minúsculas sin acentos.
  Las fotos que sube la usuaria (historia/carrusel) se **comprimen antes de guardarse** en
  `localStorage` (para no llenar el navegador). El hero NO usa `loading="lazy"` (o no cargaría).

## Reglas duras / preferencias de Maya
- **Español con puntuación completa:** `¿…?` y `¡…!` de apertura y cierre. En inglés solo el de cierre.
- **Textos cortos y cálidos**, acordes a marca de imagen pública.
- **Sin cobro y sin login.** Nada de pagos ni cuentas.
- **Mobile-first**: debe verse bien en celular.
- **Antes de cualquier acción que puedan hacer Maya o Claude, preguntar "¿lo hago yo o lo haces tú?"**

## Publicación (ya está en línea)
- Repo: `github.com/mayarsolares-bit/planificador-pilares` (rama `main`).
- Sitio: **https://planificador-pilares.vercel.app** — cada push a `main` se **auto-publica** en Vercel.
- Subir cambios: `gh` portátil en `C:\Users\mayas\tools\bin\gh.exe` (autenticado como `mayarsolares-bit`).
  Flujo: editar → `git add <archivos>` → commit → `git push origin main`.
  **No usar `git add -A`** (el `.docx` no debe publicarse).

## Previsualizar en local
- Lo más simple para Maya: **doble clic en `index.html`**.
- El panel de navegador integrado bloquea `file://`; para verlo ahí se sirve la carpeta con un
  mini-servidor de PowerShell (`System.Net.HttpListener`) en `http://localhost:8765/`.

## Fuera de alcance
Backend, base de datos, pagos, login, e IA en vivo (las ideas/contenido las escribe la usuaria).
