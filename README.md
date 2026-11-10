# SAIC50 — web version / versión web

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24106193.svg)](https://doi.org/10.5281/zenodo.24106193)

Static build of [SAIC50](https://github.com/auroragonzalez/saic50-code), a Shiny
application for estimating the IC50, compiled to WebAssembly with
[Shinylive](https://posit-dev.github.io/r-shinylive/). It needs no Shiny
Server: any static hosting service can serve this folder as it is
(publish directory: the repository root, no build command). The app runs
entirely in the browser, so data files never leave the user's computer.

*Versión web estática de SAIC50. No necesita Shiny Server: basta con servir
esta carpeta tal cual en cualquier hosting estático (directorio de
publicación: la raíz, sin comando de build). La app se ejecuta en el navegador
y los datos no salen del ordenador del usuario.*

Do not edit these files by hand. To update them, run `Rscript build_web.R`
in the source repository. / *No editar a mano: se regeneran con
`Rscript build_web.R` en el repositorio de la app.*

To test locally / *Para probar en local*:

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deployment / Despliegue

webR compiles R to WebAssembly in the browser, so the server's
`Content-Security-Policy`, if any, must allow `'unsafe-eval'` in `script-src`.
Otherwise the app never finishes loading. The included `Dockerfile` and
`nginx.conf` serve the site with nginx and a compatible CSP. In Coolify, use
the **Dockerfile** build pack (not *Static*), port 80.

*webR necesita `'unsafe-eval'` en `script-src` de la cabecera CSP; si el
servidor no lo permite, la app se queda cargando. El `Dockerfile` y
`nginx.conf` incluidos sirven la web con nginx y una CSP compatible. En
Coolify: build pack **Dockerfile** (no *Static*), puerto 80.*

Sección de Apoyo Estadístico (SAI), Universidad de Murcia. License: GPL-3.
