# Velvet Beauty

Sitio web de la marca Velvet Beauty (lencería, pijamas, perfumería, accesorios y bolsos). Proyecto final del curso de desarrollo web.

🔗 **Sitio desplegado:** https://sharongonzalezj-lgtm.github.io/Entrega5-sharongonzalez/

## Tecnologías

- HTML5 semántico
- SCSS (arquitectura modular con partials)
- Bootstrap 5.3.3 (CDN): navbar responsiva y carousel
- AOS (Animate On Scroll) para animaciones al hacer scroll
- Google Fonts (Poppins)

## Estructura del proyecto


├── index.html
├── pages/
│   ├── sobre-mi.html
│   ├── proyectos.html
│   ├── servicios.html
│   └── contacto.html
├── css/
│   └── style.css        <- generado al compilar, no se edita a mano
└── scss/
    ├── main.scss        <- único punto de entrada (@use de todos los partials)
    ├── utilities/       <- _variables.scss, _mixins.scss
    ├── base/            <- _tipografia.scss, _base.scss, _animaciones.scss
    ├── layout/          <- _header.scss, _nav.scss, _footer.scss
    └── components/      <- _buttons.scss, _cards.scss, _forms.scss


## Arquitectura SCSS

- **utilities/**: variables (paleta rosa/vino, breakpoints, tipografías) y mixins, además de los placeholders usados con `@extend`.
- **base/**: estilos globales, tipografía y animaciones (`@keyframes fadeInUp`).
- **layout/**: estructura general de la página (header, navegación, footer).
- **components/**: elementos reutilizables (banners, botones, tarjetas, carousel, formularios, secciones).

`main.scss` importa todo con `@use`. Los estilos nuevos se agregan siempre dentro del partial que les corresponde.

## Compilación

Requiere [Sass](https://sass-lang.com/install) instalado.



sass scss/main.scss css/style.css


sass --watch scss/main.scss:css/style.css


El resultado es un único `css/style.css`, vinculado desde los 5 HTML.

## Responsive

Estrategia mobile-first:

| Dispositivo | Media query |
|---|---|
| Mobile | Estilos base, sin media query |
| Tablet | `@media (min-width: 768px)` |
| Escritorio | `@media (min-width: 1024px)` |

## Animaciones

- **Nativa:** `@keyframes fadeInUp` en títulos, y `transition` en hover de tarjetas y galerías.
- **Librería:** AOS en secciones de las 5 páginas.

## SEO y accesibilidad

En esta última etapa del proyecto trabajé el SEO y la accesibilidad en las 5 páginas:

- **Títulos:** le puse a cada pagina un `<title>` propio y descriptivo, en vez de dejar nombres genéricos como "Contacto" o "Servicios".
- **Meta tags:** agregué `meta description` y `meta keywords` en el `<head>` de cada HTML, escritas segun lo que realmente contiene esa pagina.
- **Imágenes:** completé el `alt` de todas con una descripción de lo que se ve. La franja decorativa a rayas rosas la dejé con `alt` vacío, porque no aporta información y así los lectores de pantalla la saltean.
- **Nombres de archivo:** renombré las imágenes con nombres descriptivos, en minúsculas y sin `ñ`, espacios ni caracteres especiales (por ejemplo `coleccion-tease-velvet-beauty.webp`).
- **Estructura:** dejé un solo `<h1>` por pagina, con los títulos en orden (`h1`, `h2`, `h3`), y uso etiquetas semánticas como `header`, `main`, `section`, `figure` y `footer`.

### Resultados en Lighthouse (móvil)

Revisé cada página con Lighthouse en Chrome y estos fueron los puntajes:

| Página | Accessibility | SEO |
|---|---|---|
| Inicio | 95 | 100 |
| Sobre Velvet Beauty | 100 | 100 |
| Colecciones y productos | 100 | 100 |
| Servicios | 95 | 100 |
| Contacto | 96 | 100 |


## Cómo visualizarlo

Abrí `index.html` en el navegador, o visitá el sitio desplegado en el link de arriba.
