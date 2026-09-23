# Generador de rúbricas de evaluación

Aplicación web que permite crear una rúbrica de evaluación en formato Markdown a partir de los datos introducidos por el usuario.

## Cómo usar la web

Una única página (`index.html`), sin dependencias ni servidor.

1. Abre `index.html` en cualquier navegador.
2. Introduce el **título de la rúbrica**, el **número de criterios** (3–8) y el **número de niveles** (3–5) y pulsa **Generar formulario**.
3. Completa los campos generados:
   - **Niveles**: nombre y puntuación/rango de cada nivel (p. ej. `0–25`).
   - **Criterios**: título, descripción (qué se evalúa), peso (%) por criterio y la descripción de desempeño esperado en cada nivel.
4. Pulsa **Generar y descargar el .md** y se descargará el archivo Markdown con la rúbrica en formato de tabla tipo rúbrica (criterios × niveles con sus puntuaciones).

## Dónde se guarda el archivo .md

El archivo se descarga desde el navegador mediante la descarga normal del sistema: se guarda en la **carpeta de descargas** de tu equipo con un nombre derivado del título de la rúbrica (p. ej. `rubrica-de-evaluacion.md`). No se almacena en el repositorio ni se envía a ningún servidor.

Puedes consultar la vista previa del Markdown generado dentro de la propia web antes de descargarlo.

## Estructura del proyecto

- `index.html` — la aplicación web completa (interfaz + lógica en un solo archivo).
- `docs/Ejemplo/` — ejemplo de rúbrica generada con la web (también en `.pdf` y captura en `.png`).

## Entregables de la actividad

Repositorio de la tercera entrega del curso opencode: un agente de OpenCode (comandos y skills) que genera borradores de rúbricas de evaluación, más el diseño de la arquitectura y un ejemplo de ejecución.