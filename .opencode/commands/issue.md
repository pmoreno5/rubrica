#description: Crea un issue de GitHub y una rama asociada

Quiero crear un nuevo issue y su rama correspondiente.

El texto que acompaña al comando es la descripción del issue:

$ARGUMENTS

Sigue este procedimiento:

1) Analiza $ARGUMENTS y determina un título corto y descriptivo para el issue.
2) Comprueba que estamos dentro de un repositorio Git.
3) Comprueba que GitHub CLI (gh) está instalado y autenticado.
4) Comprueba el estado actual de Git con git status.
5) No elimines ni sobrescribas cambios locales existentes.
6) Crea el issue en GitHub utilizando gh issue create.
7) Obtén el número del issue creado. Dicho issue crea una rama nueva asociada a ese issue, con el siguiente formato:

feature/<numero>-<descripcion-en-kebab-case>

Si el issue corresponde claramente a un bug, utiliza:

bugfix/<numero>-<descripcion-en-kebab-case>


8) Cambia a la nueva rama utilizando:

git switch -c <nombre-rama>

9) Al finalizar, muestra:
Número del issue
Título del issue
URL del issue
Nombre de la rama asociada al issue
Rama actual

No hagas commit, push ni cierres el issue.