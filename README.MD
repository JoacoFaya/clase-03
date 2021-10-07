MARKDOWN
Un solo numeral es como un H1
Un solo numeral es como un H2
Un solo numeral es como un H3
Un solo numeral es como un H4
Un solo numeral es como un H5
Un solo numeral es como un H6
Comando de consola útiles
ls #Lista directorios en forma resumida
ls -l #Lista directorios en detallada
clear #Limpia pantalla
cd #ingreso a un directorio
cd .. #Salgo del directorio
touch #crear archivos de texto vacios
mkdir #crear directorio
Abrir directamente el VSCODE desde consola
code .
Verifico la versión de git
git --version
Configuración inicial
Por primera vez tengo hacer una configuración

git config --global user.name "Maximiliano"
git config --global user.email "mlapeducacionit@gmail.com"
Para visualizar si las configuraciones fueron efectuadas
git config --global user.name
git config --global user.email
Lista configuraciones
git config -l #lista las configuración que tengo en git (--list para mac) 
Crear repositorio local en el directorio
Aparece en la cosola en que rama estoy - main o master

git init
carpeta .git (guarda el versionado de todo el proyecto)

IMPORTANTE PELIGRO: No borrar la .git esta carpeta

GIT STATUS
Nos cuenta el estado de cada archivo en el Working Directory

git status
GIT ADD
El git agrega al staged los archivos que quiero parar prerar para la foto.

git add <nombreArchivo>
git add index.html main.html contacto.html
git add .
GIT COMMIT
Saco lo foto que me permite luego tener registro de la historia de ese archivo.

git commit
Nota: Nos abre un editor, donde podemos poner el mensaje. Depende la configuración puede ser nano, vscode o vim. NO VIM si no tienen mucha experiencia

git commit -m "Mensaje del commit"
Nota: El mensaje debe descriptivo, claro y corto. Si es funcionalidad.

GIT AMEND
Para modificar el texto descriptivo del último commit

git commit --amend #Me abre un editor donde puedo modificar el texto.
GIT LOG
git log --oneline --decorate --graph --all
GIT PULL
Nos sirve para recuperar el último commit del repo.

Recomendación: Al principio del día. Siempre hacer un git pull

GIT ALIAS
Creo alias

git config --global alias.s "status --short --branch"
Necesito editar un alias

git config --global -e
TAGS
Crear hay varias formas

git tag super-commit
Borrar tag

git tag -d super-commit
Crear tag con versión sematica

git tag -a v1.0.0 -m "Versión super-commit"
Para subir todos los tags

git push --tags
Para subir uno tag en particular

git push origin <nombre_tag>
Ejemplo

git push origin v0.8.0 a