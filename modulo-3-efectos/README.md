# Módulo 3 - Efectos

## Contenido

- [Sombras](#sombras)
- [Bordes](#bordes)
- [Gradientes](#gradientes)
- [Transiciones](#transiciones)
- [Animaciones](#animaciones)

## Sombras

```css
/* offset-x | offset-y | color */
box-shadow: 20px 16px #e3f754;

/* offset-x | offset-y | blur-radius | color */
box-shadow: 10px 5px 5px black;

/* offset-x | offset-y | blur-radius | spread-radius | color */
box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
```

- [box-shadow](https://developer.mozilla.org/es/docs/Web/CSS/box-shadow)
- [drop-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow)
- [Generador de sombras](https://shadows.brumm.af/)
- [Ejemplos de sombras](https://getcssscan.com/css-box-shadow-examples)

Lecturas recomendadas:

- [Designing Beautiful Shadows in CSS](https://www.joshwcomeau.com/css/designing-shadows/)

## Bordes

```css
/* border-width || border-style || border-color */
border: 1px solid teal;
```

- [border](https://developer.mozilla.org/es/docs/Web/CSS/border)
- [outline](https://developer.mozilla.org/es/docs/Web/CSS/outline)
- [Generador de bordes](https://html-css-js.com/css/generator/border-outline/)

```css
/* Se establece en los cuatro lados */
border-radius: 25px;

/* top-left | top-right | bottom-right | bottom-left */
border-radius: 5px 10px 20px 15px;

/* Se establecen radios adicionales con "/" para obtener esquinas elípticas */
border-radius: 10px / 20px;
```

- [border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [Generador de border-radius](https://9elements.github.io/fancy-border-radius/)

## Gradientes

```css
/* Gradiente inclinado 45 grados, con la mitad inferior izquierda negra, y una superior derecha amarilla */
background: linear-gradient(45deg, #000 0%, #e2f754 100%);
```

- [linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)

```css
/* Gradiente radial con la zona central amarilla y la exterior negra */
background: radial-gradient(circle, #e2f754 0%, #000 100%);
```

- [radial-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/radial-gradient)

```css
/* Gradiente cónico que simula un arcoiris */
background: conic-gradient(red, orange, yellow, green, blue);
```

- [conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/conic-gradient)

```css
/* Patrón de líneas  */
background: repeating-linear-gradient(
  #000,
  #000 20px,
  #e2f754 20px,
  #e2f754 25px
);
```

- [repeating-linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-linear-gradient)

- [Generador de gradientes](https://cssgradient.io/)
- [The “Gray Dead Zone” of Gradients](https://css-tricks.com/the-gray-dead-zone-of-gradients/)
- [Generador de gradientes lineales](https://www.joshwcomeau.com/gradient-generator/)

## Transiciones

```css
button {
  /* property name | duration | easing function */
  transition: transform 250ms ease-in;
}

button:hover {
  transform: translateY(-10px);
}
```

Las funciones _easing_ especifican la velocidad de transición de un parámetro a lo largo del tiempo, es decir, su aceleración. En CSS tenemos definidas una serie de [funciones easing](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function) como `ease`, `ease-in`, `ease-in-out`, etc., pero podemos definir una propia por una [curva bézier](https://css-tricks.com/advanced-css-animation-using-cubic-bezier/#aa-the-cubic-bezier-function).

- [transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
- [will-change](https://developer.mozilla.org/en-US/docs/Web/CSS/will-change)
- [Guía interactiva de transiciones](https://www.joshwcomeau.com/animation/css-transitions/)
- [Funciones easing](https://developer.mozilla.org/en-US/docs/Web/CSS/easing-function)
- [Ejemplos de funciones easing](https://easings.net/)
- [Generador de cubic-bezier](https://cubic-bezier.com/#.17,.67,.83,.67)

## Animaciones

```css
div {
  /*... */
  animation: bounce 1s ease-in-out infinite both alternate;
}

@keyframes bounce {
  from {
    top: 25%;
  }
  to {
    top: 55%;
  }
}
```

- [Usando animaciones CSS](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
  - [Guía interactiva sobre animaciones](https://www.joshwcomeau.com/animation/keyframe-animations/)
- [animation-delay](https://developer.mozilla.org/es/docs/Web/CSS/animation-delay)
- [animation-direction](https://developer.mozilla.org/es/docs/Web/CSS/animation-direction)
- [animation-duration](https://developer.mozilla.org/es/docs/Web/CSS/animation-duration)
- [animation-iteration-count](https://developer.mozilla.org/es/docs/Web/CSS/animation-iteration-count)
- [animation-name](https://developer.mozilla.org/es/docs/Web/CSS/animation-name)
- [animation-play-state](https://developer.mozilla.org/es/docs/Web/CSS/animation-play-state)
- [animation-timing-function](https://developer.mozilla.org/es/docs/Web/CSS/animation-timing-function)
- [animation-fill-mode](https://developer.mozilla.org/es/docs/Web/CSS/animation-fill-mode)

Lecturas recomendadas:

- [Cómo crear animaciones con buena performance](https://web.dev/animations-guide/)
- [Cómo medir la performance de una animación](https://medium.com/chegg/performance-monitoring-in-css-animations-f11a21d0054f)
