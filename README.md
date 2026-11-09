# SAIC50 — web version / versión web

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

Sección de Apoyo Estadístico (SAI), Universidad de Murcia. License: GPL-3.
