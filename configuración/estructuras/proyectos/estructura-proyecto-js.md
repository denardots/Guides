## Estructura de proyectos HTML, CSS y JS nativos

Cuando trabajemos con proyectos HTML, CSS y JS nativos, debemos seguir la siguiente estructura:

```bash
  public/
    css/
      normalize.css
    fonts/
      font.woff
      font.woff2
    images/
      image.webp
      svg/
        icon.svg
  src/
    css/
      style.css
    js/
      module.js
    main.js
  index.html
  README.md
  package.json
  styleint.config.js
  vite.config.js
  eslint.config.js
```

Tal como se observa, el index, README, linters y configuraciones se trabajan en la raíz del proyecto.

Los otros archivos del proyecto se dividen en dos carpetas:

## Carpeta public

Dentro de la carpeta public se colocan los archivos de apoyo como imágenes, fuentes y archivos que seran llamados directamente desde el HTML.

1. Carpeta public/css

En esta carpeta se coloca el normalize.css.

2. Carpeta public/fonts

En esta carpeta se colocan los archivos de fuentes en formato woff y woff2.

3. Carpeta public/images

En esta carpeta se colocan las imagenes en formato webp y los iconos en formato svg dentro de su propio carpeta.

## Carpeta src

Demtro de la carpeta src se colocan los archivos que serán importados y compilados en el HTML mediante el archivo main.js.

1. Carpeta src/css

En esta carpeta se coloca los estilos css.

2. Carpeta src/js

En esta carpeta se colocan los módulos de Javascript.

3. Archivo main.js

Este archivo importará a los archivos de la carpeta src como estilos, scripts; que serán compilados en el HTML.
