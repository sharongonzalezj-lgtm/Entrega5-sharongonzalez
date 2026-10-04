# Velvet Beauty

Sitio web de la marca Velvet Beauty (lencería, pijamas, perfumería, accesorios y bolsos). Proyecto final del curso de desarrollo web.

🔗 **Sitio desplegado:** https://sharongonzalezj-lgtm.github.io/Entrega5-sharongonzalez/

📁 **Repositorio:** https://github.com/sharongonzalezj-lgtm/Entrega5-sharongonzalez

## Tecnologías

- HTML5 semántico
- SCSS (arquitectura modular con partials)
- Bootstrap 5.3.3 (CDN): navbar responsiva y carousel
- AOS (Animate On Scroll) para animaciones al hacer scroll
- Google Fonts (Poppins)

## Estructura del proyecto

    ├── index.html
    ├── robots.txt
    ├── sitemap.xml
    ├── pages/
    │   ├── sobre-mi.html
    │   ├── proyectos.html
    │   ├── servicios.html
    │   └── contacto.html
    ├── assets/              <- imágenes .webp con nombres descriptivos
    ├── styles/
    │   └── main.css         <- generado al compilar, no se edita a mano
    └── scss/
        ├── main.scss        <- único punto de entrada (@use de todos los partials)
        ├── utilities/       <- _variables.scss, _mixins.scss
        ├── base/            <- _tipografia.scss, _base.scss, _animaciones.scss
        ├── layout/          <- _header.scss, _nav.scss, _footer.scss
        └── components/      <- _buttons.scss, _cards.scss, _forms.scss

## Arquitectura SCSS

- **utilities/**: variables (paleta rosa/vino, breakpoints, tipografías) y mixins, además de los placeholders usados con @extend.
- **base/**: estilos globales, tipografía y animaciones (@keyframes fadeInUp).
- **layout/**: estructura general de la página (header, navegación, footer).
- **components/**: elementos reutilizables (banners, botones, tarjetas, carousel, formularios, secciones).

El archivo main.scss importa todo con @use. Los estilos nuevos se agregan siempre dentro del partial que les corresponde.

## Compilación

Requiere [Sass](https://sass-lang.com/install) instalado.

Compilar una vez:

    sass scss/main.scss css/style.css

Compilar y quedar atento a los cambios:

    sass --watch scss/main.scss:css/style.css

El resultado es un único archivo css/style.css, vinculado desde los 5 HTML.

## Responsive

Estrategia mobile-first:

| Dispositivo | Media query |
|---|---|
| Mobile | Estilos base, sin media query |
| Tablet | @media (min-width: 768px) |
| Escritorio | @media (min-width: 1024px) |

## Animaciones

- **Nativa:** @keyframes fadeInUp en títulos, y transition en hover de tarjetas y galerías.
- **Librería:** AOS en secciones de las 5 páginas.

## SEO y accesibilidad

En esta última etapa del proyecto me enfoqué en mejorar el SEO y la accesibilidad de las 5 páginas.

**SEO on-page.** A cada página le puse un title propio que dice de qué trata, porque antes tenía títulos muy genéricos como "Contacto" o "Servicios". También agregué meta description y meta keywords en el head de cada HTML, escritas según el contenido real de cada página. Además, revisé que haya un solo h1 por página y que los títulos sigan el orden h1, h2, h3, y que la estructura use etiquetas semánticas (header, main, section, figure y footer) en vez de tantos div.

**Imágenes y accesibilidad.** Completé el alt de todas las imágenes con una descripción de lo que se ve. La franja decorativa de rayas rosas la dejé con alt vacío, porque no aporta información y así los lectores de pantalla la saltean. También renombré las imágenes con nombres descriptivos, en minúsculas y sin ñ, espacios ni caracteres especiales (por ejemplo coleccion-tease-velvet-beauty.webp). El contraste entre texto y fondo lo fui revisando con Lighthouse.

**SEO técnico.** Declaré lang="es" en todas las páginas y agregué la etiqueta canonical y los metadatos de Open Graph (og:title, og:description, og:url y og:image) para que el link se vea bien al compartirlo. También sumé un robots.txt y un sitemap.xml en la raíz del proyecto, y el sitio está publicado en GitHub Pages.

**SEO off-page y local.** Estas acciones son parte de la estrategia que pensé para la marca, pero no las apliqué porque dependen de que el negocio exista de verdad:

- Difundir el sitio desde las redes sociales de la marca (Instagram, Facebook y YouTube) con links hacia la web.
- Dar de alta la marca en Google Business Profile para aparecer en búsquedas locales.
- Usar keywords con intención local, como "lencería en Parque Patricios, CABA", ya que la dirección del local figura en el footer.

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

Abrí index.html en el navegador, o visitá el sitio desplegado en el link de arriba.
