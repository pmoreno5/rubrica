# Diseño de la arquitectura

## Objetivo

Generar un borrador de rúbrica de evaluación a partir de la descripción de una actividad evaluable, utilizando **comandos y skills de OpenCode**.

## Diseño adoptado

La arquitectura más sencilla consta de **dos elementos** con responsabilidades separadas:

| Elemento | Ruta | Responsabilidad |
|---|---|---|
| Comando `rubrica` | `.opencode/commands/rubrica.md` | Orquestar el flujo completo. |
| Skill `rubricas` | `.opencode/skills/rubricas/SKILL.md` | Aportar el conocimiento experto de diseño de rúbricas. |

No se requiere `opencode.json`: OpenCode auto-descubre comandos en `.opencode/commands/` y skills en `.opencode/skills/`.

## Comando `rubrica`

El comando es el **orquestador**: define los pasos y la interacción con el usuario, pero no contiene conocimiento de diseño.

Responsabilidades:

1. Leer el documento que describe la actividad evaluable (ruta recibida como argumento).
2. Analizar la actividad: objetivos de aprendizaje, entregables y forma de evaluación.
3. Solicitar al usuario el **número de criterios** y el **número de niveles** mediante la herramienta `question`.
4. Activar la skill `rubricas` y delegar en ella las directrices de diseño.
5. Proponer los criterios de evaluación.
6. Proponer las descripciones y valores numéricos de cada nivel.
7. Devolver la rúbrica como **tabla Markdown**.

## Skill `rubricas`

La skill es la **fuente de dominio**: define la metodología y el formato de salida. No interactúa con el usuario.

Responsabilidades:

- Reglas para definir **criterios** (3–8, medibles, observables, mutuamente excluyentes, alineados con la actividad).
- Reglas para definir **niveles** (3–5) con escala numérica coherente y descripciones con progresión clara.
- Plantilla y ejemplo de **tabla Markdown** con valores numéricos por nivel y, opcionalmente, ponderación por criterio.

## Flujo de ejecución

```
Documento de la actividad
        │
        ▼
┌─────────────────────┐   pregunta criterios/niveles   ┌────────────┐
│ Comando `rubrica`   │ ──────────────────────────────► │  Usuario   │
│ (orquestador)       │ ◄────────────────────────────── │            │
└──────────┬──────────┘        respuestas               └────────────┘
           │ activa skill `rubricas`
           ▼
┌─────────────────────┐
│ Skill `rubricas`    │  directrices de diseño
│ (dominio)           │
└──────────┬──────────┘
           ▼
   Tabla Markdown de la rúbrica
```

## Por qué esta separación

- **Responsabilidad única**: el comando sabe *cómo proceder*; la skill sabe *qué es una buena rúbrica*. Cambiar la metodología no afecta al flujo y viceversa.
- **Reusabilidad**: la skill puede invocarse desde otros comandos o trabajar sobre el documento fuente.
- **Sencillez**: cero código de aplicación; solo instrucciones en Markdown, alineado con el repositorio de la entrega.