git add .
```

Borrar un elemento y persistirlo en el repo
# Borrar un elemento y persistirlo en el repo

```bash
git rm <archivo>
@@ -114,6 +114,18 @@ Ej:
git rm Borrar.md
```

# Renombrar un archivo

```bash
git mv <archivo> <nuevoNombre>
```

Ej:

```bash
git mv nombreEquivocado.md esteEselQueva.md
```

# GIT COMMIT
Saco lo foto que me permite luego tener registro de la historia de ese archivo.

```bash
git commit
```
**Nota:** Nos abre un editor, donde podemos poner el mensaje. Depende la configuración puede ser nano, vscode o vim. NO VIM si no tienen mucha experiencia
```bash
git commit -m "Mensaje del commit"
```
**Nota:** El mensaje debe descriptivo, claro y corto. Si es funcionalidad.
**Nota2:** Cuando el archivo ya está siendo seguido por git, puedo hacer en el mismo comando add.
```bash
git commit -am "Mensaje del commit"
```
# GIT AMEND
Para modificar el texto descriptivo del último commit
```bash
git commit --amend #Me abre un editor donde puedo modificar el texto.
```
# GIT LOG
```bash
git log --oneline --decorate --graph --all
```
# GIT BRANCH
Son ramas que nos permiten seguir desarrollando funcionalidades por separado.
```bash
git branch <nombreRama>
```
Ejemplo
```bash
git branch otraRama
```
## Listar branchs
```bash
git branch #lista los branch disponibles
```
## Cambiar entre branch (checkout)
```bash
git checkout <nombreRama>
```
Ejemplo
```bash
git checkout otraRama
```
## Borrar rama
```bash
git branch -d <nombreRama>
```
## Forzar el borrado de la rama
En el caso de que la rama no haya sido fusionada (Mergeada) es necesario el forzado para borrarla
```bash
git branch -D <nombreRama>
```
## Cambiando nombre de la rama
Tengo que estar en la rama la cual quiero cambiar el nombre
```bash
git branch -mv AgregandoReadme
```
Ejemplo
```bash
git branch -d otraRama
```
## MERGE
### Escenarios MERGE
FAST-FORWARD (El mejor de los escenarios - básicamente resuelve todo git)
Uniones automaticas (Muy parecido al fast-forward)
Uniones con conflictos (Acá nosotros tenemos que decir que queda en el commit)
**IMPORTANTE** Tenemos que estar en la rama destino. O sea si yo tengo <ramaCambios> y me quiero traer los cambios de esa a la rama <master> Tengo que estar en <master> para hacer el commit
```bash
git merge <ramaCambios>
```
Ej:
Tengo ramas
* master
* ramaCambios
Me quiero traer los cambios que hay en <ramaCambios> al <master>
Me muevo a master y ejecuto el siguiente comando
```bash
git checkout master
```
```bash
git merge <ramaCambios>
```
## Crear y moverse automaticamente a la rama
```bash
git checkout -b ramaNueva
```
## Moverse entre ramas (Nuevo comando SWITCH)
Otro comando para cambiar de rama (Un comando moderno)
```bash
git switch <nombreRama>
```
Ejemplo
```bash
git switch ramaNueva
```
# GIT PULL 
Nos sirve para recuperar el último commit del repo.
**Recomendación:** Al principio del día. Siempre hacer un git pull
# GIT ALIAS
Creo alias
```bash
git config --global alias.s "status --short --branch"
```
```bash
git config --global alias.l "log --oneline --graph --all --decorate"
```
```bash
git config --global alias.lg "log --graph -- abbrev-commit --decorate --format=format:'%C (bold blue)%h%C(reset) - %C(bold green) (%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C (reset)' --all"
```
Necesito editar un alias
```bash
git config --global -e
```
# TAGS
Crear hay varias formas
```bash
git tag super-commit
```
Borrar tag
```bash
git tag -d super-commit
```
Crear tag con versión sematica
```bash
git tag -a v1.0.0 -m "Versión super-commit"
```
Para subir todos los tags
```bash
git push --tags
```
Para subir uno tag en particular
```bash
git push origin <nombre_tag>
```
Ejemplo
```bash
git push origin v0.8.0
```