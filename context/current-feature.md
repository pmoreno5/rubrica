# Feature actual

## Objetivos

- Aplicación web que genere una rúbrica de evaluación en Markdown a partir de los datos introducidos por el usuario.
- El lenguaje que requiere menos código es una **única página HTML+JS**: sin dependencias ni servidor, la descarga del `.md` se realiza desde el navegador.
- Flujo: el usuario introduce el **número de criterios** y el **número de niveles**; a continuación se itera sobre cada criterio (título y descripción) y sobre cada nivel (título y puntuación); el programa genera un archivo `.md` con toda la información recogida.

## Notas

- Issue: #1 — "Selección del lenguaje que requiere menos código"
- URL: https://github.com/pmoreno5/rubrica/issues/1
- Rama: `feature/1-seleccion-lenguaje-menos-codigo`
- Decisión adoptada: una sola página HTML+JS en la raíz del repo (`index.html`), descarga del `.md` desde el navegador, formato de salida tabla tipo rúbrica (con los niveles y sus puntuaciones).

## Histórico

- 2026-09-22: creado el issue #1 y la rama `feature/1-seleccion-lenguaje-menos-codigo`.