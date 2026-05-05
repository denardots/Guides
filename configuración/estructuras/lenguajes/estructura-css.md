## Estructura de archivos CSS

Cuando se trabaje con archivos CSS se recomienda trabajar con el paradigma mobile-first y seguir la siguiente estructura general del archivo:

```css
  /* Tipografías y Variables */
  @font-face {
    font-family: "Poppins";
  }
  :root {
    --header-color: #3b141c;
  }

  /* Estilos Generales */
  body {
    display: grid;
  }

  /* Estilos Reutilizables */
  .content-width {
    width: clamp(300px, 95%, 1300px);
  }
  /* Efectos Reutilizables */
  .social__link:hover {
    transform: scale(1.3);
  }

  /* Estilos de una parte de la página */
  .header {
    position: fixed;
  }
  /* Efectos de una parte de la página */
  .header__nav__list__link:hover {
    background-color: var(--link-color);
  }
  /* Estilos de una parte de la página utilizados por Javascript u otra librería */
  .header--inactive {
    top: 0;
  }

  /* Estilos en Tablet, PC, etc */
  @media (width >= 700px) {
    .gallery-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }
```

Adicionalmente se recomienda el siguiente orden para las propiedades en los selectores:

## Tipografía

Dentro de @font-face colocar: familia, estilo, peso, display y la ubicación de las fuentes woff2 y woff en ese orden respectivo.

```css
  @font-face {
    font-family: "Poppins";
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: url("../../public/fonts/Poppins-400.woff") format('woff2');
    src: url("../../public/fonts/Poppins-400.woff") format('woff');
  }
```

## Variables

Dentro de :root se recomeinda colocar colores, tamaños y finalmente otros valores de propiedades.

```css
  :root {
    /* Colores */
    --header-color: #3b141c;

    /* Tamaños */
    --s-size: 0.5rem;
  
    /* Otros valores de propiedades */
    --transition: 0.3s ease;
  }
```

## Resto de Selectores

Para el orden de las propiedades dentro del resto de selectores se recomienda seguir la siguiente estructura:

```css
  .clase {
    /* Propiedades de posicionamiento */
    position: fixed;
    top:0;
    z-index: 2;

    /* Propiedades de display */
    display: flex;
    justify-content: space-between;
    gap: 1rem;

    /* Propiedades de dimensiones */
    width: 100%;
    height: 4rem;

    /* Propiedades de box model */
    margin: 0 auto;
    padding: 1rem;

    /* Propiedades de tipografía */
    text-align: center;
    font-size: 2rem;
    text-transform: uppercase;

    /* Propiedades de colores */
    color: #345454;
    border: 1px solid #345454;
    background-color: var(--header-color);

    /* Propiedades especiales */
    filter: blur(5px);
    cursor: pointer;
    box-shadow: 0 0 1rem #345454;

    /* Propiedades de animaciones y transiciones */
    transition: 0.3s ease;
  }
```