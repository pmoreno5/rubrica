# Ejemplo de ejecución

Ejemplo real del agente generando una rúbrica a partir del documento `README.md` (el trabajo entregable de la actividad) mediante:

```
/rubrica README.md
```

## Documento de entrada

`README.md` describe una única entrega de la asignatura: no contiene detalles de una actividad específica. Por ello, el agente pide al usuario la descripción de la actividad antes de continuar.

> **Actividad declarada por el usuario:** "Trabajo práctico de la asignatura: implementar un agente de OpenCode compuesto por comandos y skills que genere borradores de rúbricas de evaluación, junto con su documento de diseño y un ejemplo de ejecución."

## Diálogo del agente

**Agente** — Análisis de la actividad:

> Actividad evaluable: implementación de un agente de OpenCode (comandos + skills) que genera rúbricas de evaluación, más su documento de diseño y un ejemplo de ejecución. Objetivos: diseñar una arquitectura, implementarla con OpenCode y demostrar el resultado.

**Agente** — Pregunta al usuario mediante la herramienta `question`:

> ¿Cuántos criterios de evaluación quieres? → **4**
> ¿Cuántos niveles de desempeño quieres? → **4**

**Agente** — Aplica la skill `rubricas` y propone la rúbrica:

## Rúbrica generada (salida del agente)

| Criterio | Descripción | Nivel 1 (0–25) | Nivel 2 (26–50) | Nivel 3 (51–75) | Nivel 4 (76–100) | Peso (%) |
|---|---|---|---|---|---:|---:|
| Documento de diseño | Arquitectura documentada con responsabilidad de cada comando/skill. | No se entrega o es incoherente. | Describe los elementos sin responsabilidades claras. | Arquitectura clara con responsabilidades definidas. | Arquitectura bien documentada y justificada. | 25 |
| Implementación | Comandos y skills implementados según el diseño. | No hay implementación. | Implementación parcial o desalineada con el diseño. | Implementación completa y alineada con el diseño. | Implementación completa, robusta y reutilizable. | 35 |
| Ejemplo de ejecución | Ejemplo real con rúbrica Markdown generada. | No se entrega. | Ejemplo incompleto o sin rúbrica Markdown. | Ejemplo completo con rúbrica Markdown. | Ejemplo completo, reproducible y documentado. | 20 |
| Calidad de la rúbrica | La rúbrica generada es correcta y útil. | No se genera o es inválida. | Se genera con errores de formato o contenido. | Tabla Markdown correcta y alineada con la actividad. | Tabla excelente, con niveles bien diferenciados. | 20 |

## Resultado

| Número del issue | Título | URL |
|---|---|---|
| 1 | Selección del lenguaje que requiere menos código | https://github.com/pmoreno5/rubrica/issues/1 |