## Estructura de archivos JavaScript

Cuando se trabaje con archivos JS se recomienda trabajar con módulos y seguir la siguiente estructura general del archivo:

```js
  // Obligatorio uso de: "use strict"
  "use strict";

  // Importaciones de librerías, modulos y estilos
  import Swiper from "swiper";
  import {Navigation, Pagination} from "swiper/modules";
  import "./css/style.css";

  // Declaración de clases de objetos
  class Persona {
    constructor(nombre) {
      this.nombre = nombre;
    }
  }

  // Funciones síncronas y/o asíncronas
  const loadProduct = async code => {
    let url = "../model/load_product.php";
  };

  // Declaración de constantes y variables
  const header = document.getElementById("header");
  let url = "../model/load_product.php";

  // Listeners del DOM
  menuOpenButton.addEventListener("click", () => {
    nav.classList.toggle("header__nav--active");
  });

  // Código normal, no listner, funciones, etc
  const swiper = new Swiper(".swiper", {
    modules: [Navigation, Pagination]
  });

  swiper.spacesBetween = 25;
```
