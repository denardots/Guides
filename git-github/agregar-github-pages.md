# Guía de Despliegue en GitHub Pages

Para desplegar nuestro proyecto en GitHub Pages debemos tener un proyecto creado con Vite y no tener instalado Stylelint y ESLint en el proyecto.

Se recomienda configurar Github Pages luego de crear el proyecto con Vite y configurar los linters, pero antes del desarrollo del proyecto

## Despliegue en GitHub Pages

1. Creamos nuestro proyecto con Vite y creamos nuestro repositorio local en Git

2. Creamos el commit inicial y subimos nuestro repositorio a Github mediante Visual Studio Code

3. Ingresamos a Setting->Pages dentro de la configuración del repositorio de GitHub

4. Elegimos GitHub Actions y click en Configure de GitHub Pages Jekyll

5. Eliminamos el contenido del archivo y pegamos el siguiente código de la pagina oficial de Vite:

```yml
  # Simple workflow for deploying static content to GitHub Pages
  name: Deploy static content to Pages

  on:
    # Runs on pushes targeting the default branch
    push:
      branches: ['main']

    # Allows you to run this workflow manually from the Actions tab
    workflow_dispatch:

  # Sets the GITHUB_TOKEN permissions to allow deployment to GitHub Pages
  permissions:
    contents: read
    pages: write
    id-token: write

  # Allow one concurrent deployment
  concurrency:
    group: 'pages'
    cancel-in-progress: true

  jobs:
    # Single deploy job since we're just deploying
    deploy:
      environment:
        name: github-pages
        url: ${{ steps.deployment.outputs.page_url }}
      runs-on: ubuntu-latest
      steps:
        - name: Checkout
          uses: actions/checkout@v4
        - name: Set up Node
          uses: actions/setup-node@v4
          with:
            node-version: 20
            cache: 'npm'
        - name: Install dependencies
          run: npm ci
        - name: Build
          run: npm run build
        - name: Setup Pages
          uses: actions/configure-pages@v4
        - name: Upload artifact
          uses: actions/upload-pages-artifact@v3
          with:
            # Upload dist folder
            path: './dist'
        - name: Deploy to GitHub Pages
          id: deployment
          uses: actions/deploy-pages@v4
```

6. Hacemos un commit y luego un pull en nuestro repositorio local

7. Creamos el archivo ***vite.config.js*** agregamos el siguiente código:

```js
  import {defineConfig} from "vite";

  export default defineConfig({
    // Agregamos esta línea: base + : + "https:// + nombre de la cuenta + .github.io/ + nombre del repositorio"
    base: "https://denardots.github.io/prueba"
  });
```

8. Luego desarrollamos nuestro proyecto y hacemos un commit y push a nuestro repositorio remoto

9. Fianlmente, cuando escribamos el siguiente comando en la terminal se subirá nuestro proyecto a Github Pages

```bash
  npm run build
```

10. Cada vez que subamos el proyecto a producción debemos quitar estas lineas del package.json, solo las volveremos a agregar cuando estemos en desarrollo

```json
"devDependencies": {
    // Eliminamos las líneas de los linters
    "@eslint/js": "^9.20.0",
    "@html-eslint/eslint-plugin": "^0.35.0",
    "@html-eslint/parser": "^0.35.0",
    "eslint": "^9.20.1",
    "eslint-config-standard": "^17.1.0",
    "eslint-plugin-import": "^2.31.0",
    "stylelint": "^16.14.1",
    "stylelint-config-standard": "^37.0.0",
    // Hasta aquí
    "vite": "^6.1.0",
    "vite-plugin-eslint": "^1.8.1",
    "vite-plugin-stylelint": "^6.0.0"
  }
  