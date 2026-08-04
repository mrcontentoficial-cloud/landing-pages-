# Landing Pages

Repositorio central de landing pages de MR Content / DML Médica.
Cada landing vive en su propia carpeta con un `index.html` autónomo.

## Landings

| Landing | Carpeta | Descripción |
|---|---|---|
| **Plantilla base (formulario)** | [`_plantilla-formulario/`](_plantilla-formulario/) | Plantilla reutilizable. Formulario multipaso (datos → red social → preguntas). **No es una landing final**, es el punto de partida para las demás. |
| Giveaway DML Médica | [`dml-encuesta-giveaway/`](dml-encuesta-giveaway/) | Formulario multipaso de participación en el giveaway del kit acuático (aro salvavidas + boya). |

## Crear una landing nueva a partir de la plantilla

1. **Copia** la carpeta `_plantilla-formulario/` y renómbrala con el nombre de la campaña
   (ej. `giveaway-camillas`). Se sube así: `<nombre>/index.html`.
2. Abre el `index.html` y busca con **Ctrl+F** el texto `✏️ CAMBIA`. Edita solo esas zonas:
   - **título de la pestaña** (`<title>`)
   - **imagen de portada** (el `src` de la imagen) + su descripción
   - **título del premio** en la portada
   - **preguntas del Paso 3** (puedes cambiar el texto de las preguntas)
   - **mensaje de agradecimiento**
3. Los **Pasos 1 (datos personales) y 2 (red social)** son la base universal: no se tocan.

> **Ojo:** el "motor" del formulario (los 3 pasos, la validación y el confetti) va en el
> `<script>` y **no se edita**. Si necesitas **agregar o quitar** preguntas del Paso 3
> (no solo cambiar el texto), hay que ajustar también `validateStep(3)` y `blurTests` en el
> script — para eso mejor pídele a Claude que lo haga.

## Nota sobre el formulario

Por ahora el formulario **valida los campos pero no guarda las respuestas** en ningún lado
(al enviar solo muestra la pantalla de "¡Gracias!"). Para que los datos lleguen a algún
destino (Odoo/CRM, Google Sheets, correo, etc.) hay que conectarlo — pendiente.

## Publicación

Si se activa **GitHub Pages** (rama `main`, carpeta raíz), cada landing queda disponible en:

```
https://mrcontentoficial-cloud.github.io/landing-pages-/<carpeta>/
```
