## Estructura de archivos HTML

Cuando se trabaje con archivos HTML se recomienda seguir la siguiente estructura:

```html
  <!DOCTYPE html>
  <html lang="es">
    <head> 
      <title>"Título de la página"</title>
      <!-- Metadatos -->
      <meta name="description" content="Descripción de la página">
      <meta property="og:type" content="website">
      <!-- Ícono -->
      <link rel="icon" href="public/images/svg/icon.ico">
      <!-- Normalize CSS -->
      <link rel="stylesheet" href="public/css/normalize.css">
    </head>
    <body>
      <!-- Encabezado -->
      <header>
          <nav>
            <!-- Contenido del encabezado -->
          </nav>
      </header>

      <!-- Principal -->
      <main>
        <!-- Contenido principal de la página -->
      </main>

      <!-- Secciones -->
      <section>
        <article>
          <!-- Contenido del artículo o sección -->
        </article>
      </section>

      <!-- Pie de página -->
      <footer>
        <!-- Contenido de Copyright -->
          <p>&copy; Todos los derechos reservados</p>
      </footer>

      <!-- Finalmente el script JS de tipo mód -->
      <script type="module" src="/src/main.js"></script>
    </body>
  </html>
```
