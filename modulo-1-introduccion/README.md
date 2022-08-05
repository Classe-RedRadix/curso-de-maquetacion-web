# Módulo 1 - Introducción

## Contenido

- [HTML semántico](#html-semántico)
- [Accesibilidad](#accesibilidad)
- [Atributos ARIA](#atributos-aria)
  - [Contraste de color](#contraste-de-color)
  - [Elementos activos](#elementos-activos)
    - [Herramientas para testear accesibilidad web](#herramientas-para-testear-accesibilidad-web)
- [Trabajando con diseño](#trabajando-con-diseño)
  - [Software de handoff](#software-de-handoff)
  - [Un vistazo a Figma](#un-vistazo-a-figma)
- [CSS avanzado](#css-avanzado)
  - [Reset CSS](#reset-css)
  - [Custom properties](#custom-properties)
  - [Unidades de medida y operaciones](#unidades-de-medida-y-operaciones)
    - [Viewport units](#viewport-units)
    - [calc()](#calc)
  - [Media queries](#media-queries)
- [Imágenes](#imágenes)
  - [figure y figcaption](#figure-y-figcaption)
  - [Imágenes responsive](#imágenes-responsive)
    - [srcset](#srcset)
    - [picture](#picture)
  - [Proporciones](#proporciones)
  - [Aspect ratio](#aspect-ratio)
- [Formularios](#formularios)
- [Tipografía](#tipografía)
  - [Cargar fuentes](#cargar-fuentes)
    - [font-face](#font-face)
    - [import](#import)
    - [link](#link)

## HTML semántico

Escribir HTML semántico permite que nuestro código sea más legible, además de mejorar la interpretación de los lectores de pantalla, por lo que es beneficioso también en términos de accesibilidad.

- [Elementos HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) para usar como referencia.
- [Caninclude](https://caninclude.glitch.me/) para verificar qué elementos HTML pueden anidarse.

## Accesibilidad

Accesibilidad Web significa que sitios web, herramientas y tecnologías están diseñadas y desarrolladas de tal manera que las personas con discapacidades pueden usarlas. Más concretamente, que puedan: percibir, comprender, navegar e interactuar con la web, además de contribuir en ella.

Abarca todas las discapacidades que afectan al acceso a la web, incluyendo auditivas, cognitivas, neurológicas, físicas, del habla y visuales. Y no solo discapacidades: personas con limitación por su ubicación, conexión a internet, personas mayores, etc.

_Fuente: [W3C](https://www.w3.org/WAI/fundamentals/accessibility-intro/es#what)_

- [a11yphant](https://a11yphant.com/), una introducción a la accesibilidad.
- [Recursos de a11y project](https://www.a11yproject.com/resources/) para conocer más.

## Atributos ARIA

ARIA significa **Accessible Rich Internet Applications** y se usa para añadir información semántica a los elementos de un sitio web. Existen tres tipos de elementos principales:

- **Roles**: define el tipo de elemento mediante `role=”role_name”`, por ejemplo `button`, `checkbox`, `dialog`, `link`, `tab`, `menu`, etc.
- **Estados**: cambian en función de la interacción del usuario, por ejemplo `aria-checked` y `aria-disabled`.
- **Propiedades**: no cambian con la interacción del usuario, por ejemplo `aria-label` y `aria-hidden`.

Ejemplos de uso:

```html
<!-- Botón con solo un icono -->
<button aria-label="Cerrar">
  <svg focusable="false" aria-hidden="true" viewBox="0 0 24 24">
    <path
      d="M19 6.41L17.59 5 12 10.59 6.41 5 5
         6.41 10.59 12 5 17.59 6.41 19 12
         13.41 17.59 19 19 17.59 13.41 12z"
    />
  </svg>
</button>
```

```html
<!-- Inupt sin label -->
<input
  type="text"
  name="name"
  placeholder="¿Cuál es tu email?"
  aria-label="Tu email"
/>
```

- [ARIA Authoring Practices document](https://www.w3.org/TR/wai-aria-practices-1.1/) recoge buenas prácticas para usar roles y propiedades ARIA.
- [Cinco reglas de ARIA](https://www.w3.org/TR/using-aria/#NOTES) para tener en cuenta si queremos que nuestra web sea accesible.

### Contraste de color

- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Simulador de daltonismo](https://www.colorhexa.com/008000#blindness-simulator)

### Elementos activos

- [focus-visible](https://developer.mozilla.org/es/docs/Web/CSS/:focus-visible)
- [focus-within](https://developer.mozilla.org/es/docs/Web/CSS/:focus-within)
- [A guide to designing accessible, WCAG-compliant focus indicators](https://www.sarasoueidan.com/blog/focus-indicators/), por [Sara Soueidan](https://www.sarasoueidan.com/).

#### Herramientas para testear accesibilidad web

- [Pa11y](https://pa11y.org/), para ejecutarlo directamente desde la terminal, por ejemplo `npx pa11y https://github.com`
- [Lighthouse](https://github.com/GoogleChrome/lighthouse), para usarlo desde terminal o con la extensión de Chrome.
- [Wave](https://wave.webaim.org/), una de las extensiones para navegadores más completas.

## Trabajando con diseño

### Software de handoff

- [Sketch](https://www.sketch.com/)
- [Zeplin](https://zeplin.io/)
- [InVision](https://www.invisionapp.com/)
- [Framer](https://www.framer.com/)
- [Figma](https://www.figma.com/)

### Un vistazo a Figma

- [Ant Design](https://www.figma.com/community/file/831698976089873405), un sistema de diseño open source.

## CSS avanzado

### Reset CSS

- El clásico [CSS Reset](https://meyerweb.com/eric/tools/css/reset/) de [Eric Meyer](https://meyerweb.com/eric/).
- Una [versión más moderna](https://piccalil.li/blog/a-modern-css-reset/), explicada al detalle.

### Custom properties

```css
:root {
  --primary-color: teal;
}

section {
  background-color: var(--primary-color);
}

button {
  border: 1px solid var(--primary-color);
}
```

- [Custom properties](https://developer.mozilla.org/es/docs/Web/CSS/Using_CSS_custom_properties)

### Unidades de medida y operaciones

#### Viewport units

- [Artículo sobre viewport units](https://ishadeed.com/article/viewport-units/)

#### calc()

```css
div {
  width: calc(100% - 80px);
}
```

- [calc()](https://developer.mozilla.org/es/docs/Web/CSS/calc)
- [Guía completa de calc()](https://css-tricks.com/a-complete-guide-to-calc-in-css/)

### Media queries

```css
/* Cuando el navegador tiene al menos 600px */
@media screen and (min-width: 600px) {
  div {
    /* Estilos */
  }
}
```

- [Guía completa sobre media queries](https://css-tricks.com/a-complete-guide-to-css-media-queries/)
- [prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
- [prefers-color-scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)

## Imágenes

### figure y figcaption

```html
<figure>
  <img
    src="starry-night.jpg"
    alt="An abstract painting with a weird squiggly tree thing in front of a swirling starry nighttime sky."
  />
  <figcaption>
    The Starry Night, a famous painting by Vincent van Gogh
  </figcaption>
</figure>
```

### Imágenes responsive

- [Guía sobre imágenes responsive con HTML](https://css-tricks.com/a-guide-to-the-responsive-images-syntax-in-html/)

#### srcset

En función de la densidad de píxeles:

```html
<img
  alt="A dog swimming on the beach"
  srcset="/dog1x.jpg 1x, /dog2x.jpg 2x, /dog3x.jpg 3x, /dog4x.jpg 4x"
  src="/dog-fallback.jpg"
/>
```

En función del tamaño:

```html
<img
  alt="A dog swimming on the beach"
  srcset="/dog1x.jpg 200w, /dog2x.jpg 300w, /dog3x.jpg 400w, /dog4x.jpg 500w"
  src="/dog-fallback.jpg"
/>
```

#### picture

```html
<picture>
  <source srcset="dog-zoomed-out.jpg" media="(min-width: 1000px)" />
  <source srcset="dog.jpg" media="(min-width: 600px)" />
  <img src="dog-zoomed-in.jpg" alt="A dog swimming on the beach" />
</picture>
```

### Proporciones

```css
img {
  object-fit: cover; /* fill | contain | cover | none | scale-down */
}
```

- [object-fit](https://css-tricks.com/almanac/properties/o/object-fit/)

```css
img {
  object-position: right bottom; /* Porcentaje o valores top | left | right | bottom */
}
```

- [object-position](https://css-tricks.com/almanac/properties/o/object-position/)

### Aspect ratio

```css
div {
  aspect-ratio: 1 / 1; /* Cuadrado */
}
```

- [aspect-ratio](https://css-tricks.com/almanac/properties/a/aspect-ratio/)

## Formularios

- [Inputs y textareas](https://moderncss.dev/custom-css-styles-for-form-inputs-and-textareas/)
- [Radio buttons](https://moderncss.dev/pure-css-custom-styled-radio-buttons/)
- [Checkbox](https://moderncss.dev/pure-css-custom-checkbox-style/)
- [Select](https://moderncss.dev/custom-select-styles-with-pure-css/)
- [Buenas prácticas desde la perspectiva de diseño](https://gerireid.com/forms.html)

## Tipografía

### Cargar fuentes

#### font-face

Se usa normalmente para cargar fuentes locales.

```css
@font-face {
  font-family: Lato;
  src: url("path-to-lato.woff2") format("woff2"), url("path-to-lato.woff")
      format("woff");
}

@font-face {
  font-family: Lato;
  src: url("path-to-lato-bold.woff2") format("woff2"), url("path-to-lato-bold.woff")
      format("woff");
  font-weight: 700;
}

@font-face {
  font-family: Lato;
  src: url("path-to-lato-italic.woff2") format("woff2"), url("path-to-lato-italic.woff")
      format("woff");
  font-style: italic;
}

@font-face {
  font-family: Lato;
  src: url("path-to-lato-bold-italic.woff2") format("woff2"), url("path-to-lato-bold-italic.woff")
      format("woff");
  font-weight: 700;
  font-style: italic;
}
```

#### import

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@500&display=swap");

body {
  font-family: "Open Sans", sans-serif;
}
```

#### link

```html
<link rel="preconnect" href="<https://fonts.googleapis.com>" />
<link rel="preconnect" href="<https://fonts.gstatic.com>" crossorigin />
<link
  href="<https://fonts.googleapis.com/css2?family=Open+Sans:wght@500&display=swap>"
  rel="stylesheet"
/>
```

```css
body {
  font-family: "Open Sans", sans-serif;
}
```

- [Google Fonts](https://fonts.google.com/)
- [Buenas prácticas](https://web.dev/font-best-practices/)
