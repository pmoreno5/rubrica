---
name: rubricas
description: Diseña rúbricas de evaluación. Úsala cuando el usuario pida generar una rúbrica, criterios de evaluación, niveles de desempeño, valores numéricos por nivel, o cuando trabaje con activity-3.md o con el comando /rubrica.
---

# Diseño de rúbricas de evaluación

Esta skill aporta el conocimiento experto para construir rúbricas de evaluación a partir de la descripción de una actividad evaluable. El comando `/rubrica` orquesta el flujo; esta skill define qué hace una buena rúbrica y cómo se formatea.

## Criterios de evaluación

- Definir entre **3 y 8 criterios**. Si el usuario indicó un número concreto, respetarlo.
- Cada criterio debe estar **alineado con la actividad** y sus objetivos de aprendizaje.
- Los criterios deben ser **medibles, observables y mutuamente excluyentes** (sin solaparse).
- Nombre corto y descriptivo + una frase que precise qué se evalúa.

## Niveles y valores numéricos

- Definir entre **3 y 5 niveles**. Si el usuario indicó un número concreto, respetarlo.
- Usar una **escala numérica coherente**, normalmente 0–100 repartida en rangos iguales por nivel, o ponderada por criterio.
- Cada nivel lleva una **descripción del desempeño esperado** para ese criterio, escrita en presente de indicativo y específica de la actividad.
- Las descripciones de niveles contiguos deben marcar una **progresión clara** (de menor a mayor logro).
- Incluir una columna **Peso (%)** por criterio si la rúbrica suma 100 %.

## Formato de salida (tabla Markdown)

Use esta plantilla como referencia y adjúste los nombres de los niveles a la escala elegida:

```markdown
| Criterio | Descripción | Nivel 1 (0–25) | Nivel 2 (26–50) | Nivel 3 (51–75) | Nivel 4 (76–100) | Peso (%) |
|---|---|---|---|---|---:|---:|
| <criterio> | <qué se evalúa> | <desempeño nivel 1> | <desempeño nivel 2> | <desempeño nivel 3> | <desempeño nivel 4> | <0–100> |
```

- Si la escala es 1–4 (sin porcentajes), omitir la columna **Peso (%)** y usar `Nivel 1`…`Nivel 4` como encabezados.
- Mantener la rúbrica en **español** salvo que el usuario indique lo contrario.

## Ejemplo

Actividad: "Exposición oral de 10 minutos sobre un tema del curso, con apoyo visual."

| Criterio | Descripción | Nivel 1 (0–25) | Nivel 2 (26–50) | Nivel 3 (51–75) | Nivel 4 (76–100) | Peso (%) |
|---|---|---|---|---|---:|---:|
| Contenido | Dominio del tema y precisión de la información. | La información es escasa o contiene errores relevantes. | Presenta la información básica con algunos errores. | Información completa y precisa, con matices. | Información completa, precisa y profundizada. | 40 |
| Estructura | Organización de la exposición (introducción, desarrollo, cierre). | Sin estructura clara; discurso desordenado. | Estructura parcial con transiciones débiles. | Estructura clara y coherente. | Estructura cuidada que refuerza el mensaje. | 30 |
| Apoyo visual | Calidad y uso de los materiales de apoyo. | Sin apoyo o irrelevante. | Apoyo básico que acompaña la exposición. | Apoyo adecuado y bien integrado. | Apoyo excelente que enriquece la exposición. | 30 |