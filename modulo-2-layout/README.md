# Módulo 2 - Layout

## Contenido

- [Posicionamiento](#posicionamiento)
- [Buenas prácticas](#buenas-prácticas)
- [Metodologías y arquitecturas CSS](#metodologías-y-arquitecturas-css)
  - [Convenciones de nombres de clases](#convenciones-de-nombres-de-clases)
  - [Arquitecturas](#arquitecturas)
- [Flexbox](#flexbox)
- [Grid](#grid)
- [Ejemplos de layouts](#ejemplos-de-layouts)
- [Scroll](#scroll)
  - [Smooth scroll](#smooth-scroll)
  - [Scroll snap](#scroll-snap)
- [Estructuras de proyectos](#estructuras-de-proyectos)

## Posicionamiento

- [relative](https://css-tricks.com/almanac/properties/p/position/)
- [absolute](https://css-tricks.com/almanac/properties/p/position/#aa-absolute)
- [fixed](https://css-tricks.com/almanac/properties/p/position/#aa-fixed)
- [sticky](https://css-tricks.com/almanac/properties/p/position/#aa-sticky)

## Buenas prácticas

- Principio de **responsabilidad única** o **DRY** (Don't Repeat Yourself). Podrás hacer cambios más fáciles y seguros modificando menos líneas de código.

- No intentes **optimizar prematuramente** tu código: mantenlo legible.

- Solo debe existir un **formato** en todo el código: elijas espacios o tabulaciones, su uso debe ser consistente en el proyecto. Puedes usar herramientas como [Prettier](https://prettier.io/) para formatearlo.

- **Ordena** las declaraciones para mejorar la consistencia y legibilidad, por ejemplo:

  1. Caja: \*\*\*\*`margin, padding, display, etc.`
  2. Bordes y fondos: \*\*\*\*`border, border-radius, background-color, etc.`
  3. Texto: \*\*\*\*`color, font-size, text-transform, etc.`
  4. Otros: \*\*\*\*`animations, transforms, etc.`

- Mantén la **especificidad baja**. Si sientes que estás sobreescribiendo demasiado o usando selectores complejos como `.posts article h2:not(:first-child) { }` deberías parar y considerar la arquitectura.

- **Piensa en componentes**. Ve de menos a más, definiendo los componentes básicos necesarios para construir la web. Metodologías como [Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/) te ayudarán a ello.

- **Define temas** con _custom properties_. A través de las custom properties podemos almacenar muchos valores reutilizables como colores, espaciados, transiciones, etc. y hacer el código más legible y mantenible.

  ```css
  :root {
    --color-primary: #f5005e;
    --spacing-m: 16px;
  }

  body {
    padding: var(--spacing-m);
    color: var(--color-primary);
  }
  ```

Lecturas recomendadas:

- [The single responsibility principle applied to CSS](https://csswizardry.com/2012/04/the-single-responsibility-principle-applied-to-css/)
- [Strategies for Keeping CSS Specificity Low](https://css-tricks.com/strategies-keeping-css-specificity-low/)
- [Principles of writing consistent, idiomatic CSS](https://github.com/necolas/idiomatic-css)
- [CSS Architecture](https://philipwalton.com/articles/css-architecture/)

## Metodologías y arquitecturas CSS

- **Arquitectura** se centra más en la organización de carpetas.
- **Metodología** se centra más en la implementación y sintaxis (por ejemplo, cómo nombrar clases).

### Convenciones de nombres de clases

- [BEM](http://getbem.com/)

### Arquitecturas

- [SMASS](http://smacss.com/)
- [OOCSS](https://github.com/stubbornella/oocss/wiki)
- [ITCSS](https://itcss.io/)

Lecturas recomendadas:

- [BEMIT: Taking the BEM Naming Convention a Step Further](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)
- [Don’t Fight the Cascade, Control It!](https://css-tricks.com/dont-fight-the-cascade-control-it/)
- [BEM cheat sheet](https://9elements.com/bem-cheat-sheet/)
- [An Introduction To Object Oriented CSS (OOCSS)](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)

## Flexbox

- [Guía de flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Playground](https://codepen.io/enxaneta/pen/adLPwv)
- [Flexbox Froggy](https://flexboxfroggy.com/), un juego para practicar.

## Grid

- [Guía de grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Playground](https://grid.layoutit.com/)
- [Grid garden](https://cssgridgarden.com/), un juego para practicar.

## Ejemplos de layouts

- [Columnas fijas](<https://web.dev/one-line-layouts/#03.-sidebar-says:-grid-template-columns:-minmax(lessmingreater-lessmaxgreater)-...>))
- [Columnas flexibles](https://web.dev/one-line-layouts/#07.-ram-(repeat-auto-minmax):-grid-template-columns(auto-fit-minmax(lessbasegreater-1fr))
- [Columnas con la misma altura](https://web.dev/one-line-layouts/#08.-line-up:-justify-content:-space-between)
- [Holy grail](https://web.dev/one-line-layouts/#05.-classic-holy-grail-layout:-grid-template:-auto-1fr-auto-auto-1fr-auto)
- [Doce columnas](<https://web.dev/one-line-layouts/#06.-12-span-grid:-grid-template-columns:-repeat(12-1fr)>)

Lecturas recomendadas:

- [Understanding Layout Algorithms](https://www.joshwcomeau.com/css/understanding-layout-algorithms/)
- [Less Absolute Positioning With Modern CSS](https://ishadeed.com/article/less-absolute-positioning-modern-css/)

## Scroll

### Smooth scroll

```css
html {
  scroll-behavior: smooth;
}
```

### Scroll snap

```css
.container {
  scroll-snap-type: y mandatory;
}

.child {
  scroll-snap-align: center;
}
```

`scroll-snap-type` le indica el contenedor cómo se ajustará al hacer scroll. El primer parámetro corresponde al eje sobre el que se ajustará el scroll y el segundo al tipo de ajuste, que puede ser `mandatory` o `proximity`.

- `mandatory`: al hacer scroll se ajusta siempre.
- `proximity`: al hacer scroll se ajusta solo cuando el scroll esté muy próximo al punto de ajuste.

En [este ejemplo de CodePen](https://codepen.io/maxakohler/pen/ZjrOpx) puedes ver la diferencia entre ambas opciones.

## Estructuras de proyectos

- [Cómo crear un boilerplate con Parcel](https://parceljs.org/languages/css/)
- [GitHub pages](https://pages.github.com/)
