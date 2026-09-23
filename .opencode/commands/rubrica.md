---
description: Genera un borrador de rúbrica de evaluación a partir de un documento que describe una actividad evaluable.
---

Genera una rúbrica de evaluación para la actividad descrita en $ARGUMENTS.

Sigue este procedimiento:

1. Lee el documento $ARGUMENTS y analiza la actividad evaluable: objetivos de aprendizaje, entregables o tareas y forma de evaluación.
2. Responde con un breve resumen del análisis antes de continuar.
3. Pregunta al usuario el **número de criterios** y el **número de niveles** usando la herramienta `question`.
4. Carga la skill `rubricas` y sigue sus directrices para el diseño.
5. Propón los **criterios de evaluación**, indicando para cada uno su nombre y una breve descripción.
6. Propón las **descripciones y valores numéricos** de cada nivel para cada criterio.
7. Devuelve la rúbrica como **tabla en formato Markdown**, siguiendo la plantilla de la skill.

Al finalizar muestra también un breve resumen del resultado, pero sin añadir más documentos.

No crees ni modifiques archivos: la salida es la tabla Markdown en la respuesta.