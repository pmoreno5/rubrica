#description: Crea un issue de GitHub y una rama asociada

Quiero crear un nuevo issue y su rama correspondiente.

El texto que acompaña al comando es la descripción del issue:

$ARGUMENTS

Sigue este procedimiento:

Analiza $ARGUMENTS y determina un título corto y descriptivo para el issue.
Comprueba que estamos dentro de un repositorio Git.
Comprueba que GitHub CLI (gh) está instalado y autenticado.
Comprueba el estado actual de Git con git status.
No elimines ni sobrescribas cambios locales existentes.
Crea el issue en GitHub utilizando gh issue create.
Obtén el número del issue creado.

Genera un nombre de rama siguiendo este formato:

feature/<numero>-<descripcion-en-kebab-case>

Si el issue corresponde claramente a un bug, utiliza:

bugfix/<numero>-<descripcion-en-kebab-case>

Crea la rama y cambia a ella utilizando:

git switch -c <nombre-rama>

Al finalizar, muestra:
número del issue
título del issue
URL del issue
nombre de la rama
rama actual

No hagas commit, push ni cierres el issue.