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

```
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
    └── components/      <- _buttons.scss, _cards.scss, _forms.scss, ...
```

## Arquitectura SCSS

- **utilities/**: variables (paleta rosa/vino, breakpoints, tipografías) y mixins, además de los placeholders usados con `@extend`.
- **base/**: estilos globales, tipografía y animaciones (`@keyframes fadeInUp`).
- **layout/**: estructura general de la página (header, navegación, footer).
- **components/**: elementos reutilizables (botones, tarjetas, formularios, galerías).

`main.scss` importa todo con `@use`. Los estilos nuevos se agregan siempre dentro del partial que les corresponde.

## Compilación

Requiere [Sass](https://sass-lang.com/install) instalado.

```bash
# Compilar una vez
sass scss/main.scss css/style.css

# Compilar automáticamente al guardar
sass --watch scss/main.scss:css/style.css
```

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

## Cómo visualizarlo

Abrí `index.html` en el navegador, o visitá el sitio desplegado en el link de arriba.
