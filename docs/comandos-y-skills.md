# Comandos y skills de OpenCode

Documento de referencia con todos los comandos y skills de OpenCode definidos en este proyecto.

## Comandos

Los comandos se autocubren en `.opencode/commands/` y se invocan anteponiendo `/`.

| Comando | Archivo | Descripción |
|---|---|---|
| `/rubrica` | `.opencode/commands/rubrica.md` | Genera un borrador de rúbrica de evaluación a partir de un documento que describe una actividad evaluable. |
| `/issue` | `.opencode/commands/issue.md` | Crea un issue de GitHub y una rama asociada. |

### `/rubrica`

**Uso:** `/rubrica <ruta-del-documento>`

Orquesta el flujo completo de diseño de una rúbrica. Responsabilidades:

1. Leer el documento y analizar la actividad evaluable (objetivos de aprendizaje, entregables y forma de evaluación).
2. Resumir brevemente el análisis antes de continuar.
3. Preguntar al usuario el **número de criterios** y el **número de niveles** mediante la herramienta `question`.
4. Cargar la skill `rubricas` y seguir sus directrices de diseño.
5. Proponer los **criterios de evaluación** (nombre y descripción breve).
6. Proponer las **descripciones y valores numéricos** de cada nivel para cada criterio.
7. Devolver la rúbrica como **tabla en formato Markdown** siguiendo la plantilla de la skill.

No crea ni modifica archivos: la salida es la tabla Markdown en la respuesta.

### `/issue`

**Uso:** `/issue <descripción-del-issue>`

Crea un issue en GitHub con `gh` y genera una rama asociada con la convención del repositorio.

Responsabilidades:

1. Determinar un título corto y descriptivo a partir de `$ARGUMENTS`.
2. Comprobar que estamos en un repositorio Git y que `gh` está instalado y autenticado.
3. Revisar el estado con `git status` sin eliminar ni sobrescribir cambios locales.
4. Crear el issue con `gh issue create` y obtener su número.
5. Generar la rama con el formato:
   - `feature/<numero>-<descripcion-en-kebab-case>` para características.
   - `bugfix/<numero>-<descripcion-en-kebab-case>` para bugs.
6. Crear y cambiar a la rama con `git switch -c <nombre-rama>`.

Al terminar muestra número, título y URL del issue, y el nombre de la rama. No hace commit, push ni cierra el issue.

## Skills

Las skills se autocubren en `.opencode/skills/` y aportan conocimiento experto que el agente carga a petición.

| Skill | Archivo | Descripción |
|---|---|---|
| `rubricas` | `.opencode/skills/rubricas/SKILL.md` | Conocimiento experto para diseñar rúbricas de evaluación: criterios, niveles, valores numéricos y formato de salida. |

### `rubricas`

Es la fuente de dominio del diseño de rúbricas y no interactúa directamente con el usuario. La carga el comando `/rubrica`.

Directrices que aporta:

- **Criterios**: entre 3 y 8, medibles, observables y mutuamente excluyentes, alineados con la actividad.
- **Niveles**: entre 3 y 5, con escala numérica coherente (p. ej. 0–100 por rangos iguales) y descripciones con progresión clara.
- **Peso (%)**: columna opcional por criterio cuando la rúbrica suma 100 %.
- **Salida**: plantilla de tabla Markdown con una fila por criterio y columnas por nivel.

## Skills de OpenCode utilizadas

En el trabajo de configuración de este proyecto también se emplea la skill integrada de OpenCode:

- **`customize-opencode`**: guía la edición de la configuración propia de OpenCode (`opencode.json`, archivos bajo `.opencode/`), por ejemplo al crear o corregir comandos y skills.

## Resumen

| Tipo | Nombre | Origen | Responsabilidad |
|---|---|---|---|
| Comando | `rubrica` | `.opencode/commands/` | Orquestar la generación de la rúbrica. |
| Comando | `issue` | `.opencode/commands/` | Crear issue y rama asociada en GitHub. |
| Skill | `rubricas` | `.opencode/skills/` | Aportar las directrices de diseño de rúbricas. |
| Skill | `customize-opencode` | Integrada | Editar la configuración propia de OpenCode. |