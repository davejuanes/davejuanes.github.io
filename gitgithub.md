[Pagina Principal](index.md)
### Git y Github
![Git y Github](https://pythonforundergradengineers.com/posts/git/images/git_and_github_logo.png)
Estar en el mundo del desarrollo de tecnologias en cualquier tipo de rama requiere conocimientos de versionamiento, incluso para poder hacer proyectos propios a contrato o cualquiera es necesario conocer estas herramientas te dejo algunos comando que son los que mas utilizo cada dia...

- git init -> Inicializa un repositorio
- git add NombreDeArchivo.txt -> agrega el archivo a la memoria RAM
- git rm NombreArchivo.txt -> Mantiene el archivo en la memoria RAM
- git rm --cached NombreArchivo.txt -> elimina el archivo de memoria RAM
- git commit -m ‘Mensaje’ -> Envía el archivo (os) al repositorio
- git config --list -> muestra los datos de configuración
- git config --list --show-origin -> Muestra las configuración con la ubicacion
- git config --global user.name “David Gonzalo Mercado Juanes”
- git config --global user.email “davidmercado@correo.com”

Adicionalmente a estos comandos de inicio de proyectos en local y otros que serian una forma de hacer seguimiento a los archivo de tu proyecto o los cambios que hiciste en varios para ver a cuantos archivos afectaste serian los siguiente:

- git log Archivo.txt -> muestra todos los commits del archivo con su ID
- git diff 5b82d1f2f3ddb1c85b8149d99620912e1ab5678a 1397c0c6fba344b0a72e9647081b22d317e3b83b -> Muestra los cambios entre ambos commits
- git show Archivo.txt -> Muestra los datos actuales del archivo con autor peso y cambios en el mismo. Se ven cambios atomicos

### Ver todas las Branch's

Siempre queda el momento para poder ver las ramas y como fue el flujo del proyecto, para esto existe un comando muy sencillo que es:

- git log --all -> nos muestra todos los commits del proyecto
- git log --all --graph --decorate --online -> nos muestra todo comprimido con ramas cambio ademas de la historia

Ahora bien, este comando es super largo y muy dificil de recordar, para mejorar esto podemos crear un alias del mismo:
- [x] alias historia="git log --all --graph --decorate --online"

Prueba el comando, podra ayudarte siempre que tengas comandos largos

### Traer cambios de otras ramas

Para volver a otras versiones del proyecto o commits utiliza el comando “reset”, como esta a continuación:

- git reset idCommit --soft -> cambios suaves
- git reset idCommit --hard -> cambios fuertes o totales

** Git reset elimina todos los otros commit que se hicieron **

- git log stat -> muestra los cambios con en el en bits
- git checkout idCommit Archivo.txt -> muestra el archivo en ese commit
- git checkout master Archivo.txt -> muestra el archivo de esa rama
- git log --stat -> nos muestra los cambios modificados con el peso de los mismos

### Llaves publicas y llaves privadas
Estas se crean y se vinculan matematicamente para poder mostrar el contenido
Los comando para utlizar las llaves son:
Para generar una llave ssh en windows y linux se usa el siguiente comando:
- ssh-keygen -t rsa -b 4096 -C “emailGithub”
Para verificar que se este ejecutanto el agente ssh en la maquina se usa el siguiente comando:
- eval $(ssh-agent -s)
Las llaves se almacenan por defecto en la ruta home de los usuarios (c/user/nameuser/.ssh) por lo tanto se tiene que ubicar en esta ruta mediante el acortador ~:
- cd ~
Finalmente para decirle al agent que utilize nuestra llave ssh:
- ssh-add ~/.ssh/id_rsa

### Configuración del proyecto con SSH
Luego de crear la llave ya configurar el repositorio local, se tiene que agregar la llave en el repositorio de Github o Gitlab, para esto en settings -> SSH and GPG Keys -> agregamos nueva llame definimos un nombre y pegamos la llave publica generada en el repositorio, Github pedira que confirmemos con el password y listo!. Ahora nos toca configurar el proyecto para que el origin sea en base a SSH
- git remote -v -> nos muestra el origin y destino del proyecto
- git remote set-url origin ‘ruta ssh del repositorio’
- git remote -v -> ya nos mostrara la nueva ruta de origin del proyecto


### Git reset vs git rm

#### git rm
Estos comando son similares pero tiene funcionalidades muy diferentes:
- git rm --cached Archivo.txt -> Nos elimina el archivo del Staging, le dice a git que deje de tracker el archivo pero el archivo sigue en el equipo
- git rm --force Archivo.txt -> Nos eliminar el archivo del disco duro y de git

#### git reset
Este comando nos ayuda a volver en el tiempo, volvemos a versiones anteriores pero sin posibilidad de volver en el futuro (git checkout si)
- git reset --soft -> Borramos el historial de Git pero guardamos los cambios que hay en Staging para un nuevo commit.
- git reset --hard -> Borra todo, absolutamente todo.
- git reset HEAD -> Evita el envío de los archivos en Staging al último commit a menos que así lo deseemos


### Marcar versiones en el proyecto
Para poder marcar un commit como un punto de version del proyecto puedes utilizar el comando "tag", es bastante util cuando quieres definir los cambios en el proyecto pero continuar en el mismo:

- git tag -a v1.0 -m "Primera version beta" idCommitShort

Quieres ver los tags del proyecto?. Pues utiliza esto:
- git tag -> muestra todos los tags
- git show-ref --tag -> muestra el idCommit y el tag

Finalmente se tiene que enviar los tags al repositorio.
 - Primero actualizamos el repositorio
 - git push origin --tag -> Esto mostrara en Github una nueva opcion en las branch's con la primer version del proyecto
 - git tag -d version1.0 -> Este comando elimina el tag seleccionado
Esto elimina los tags de manera local, pero para poder eliminarlos de Github usa el siguiente comando:
 - git push origin :refs/tags/version1.0

Para poder ver todas las ramas podemos utilizar:
- git show-branch -> ramas existentes y su historia
- git show-branch --all -> que nos muestra todas las ramas con un poco mas de detalle
- gitk -> si quieres un modo visual para ver como funcionan las cosas
**Desde una buena practica de desarrollo lo mejor es que nosotros creemos branch's o ramas para cada tipo de trabajo que realizemos.**

Genial!, ahora veremos como traer proyectos o clone de otros proyectos **Ojo para proyectos PUBLICOS**
- git clone URL Http -> clona el repositorio con el nombre del proyecto ojo para hacer un push **Deben estar agregados al repositorio por el propietario**
Una buena practica de toda la vida, es hacer un pull de main o master luego de hacer un push al repositorio.

### Git Rebase
Es solo para repositorios locales, jamas en un repositorio oficial.
- git rebase main -> Combina las ramas donde experimentas poniendolos en la linea de vida del proyecto
Son cambios silenciosos en la vida del proyecto que pueden solucionar conflictos, pero tienes algunos contras que son: nadie sabe como pasaron las cosas, no se sabe en que momento paso, necesariamente se tiene que hacer un rebase a la rama de resolve fixes o experimentos y al final hacer un rebase en la rama master o main.

### Stash

El comando stash nos ayuda a poder almacenar en un lugar temporal los cambios que se tenian previamente. Este sitio temporal puede verse con:
- git stash list -> Muestra WIP work in progress la rama el ID del ultimo commit y el comentario de este commit
- git stash pop -> Te devuelve los cambios almacenados en el stash temporal

Ahora, si queremos poner estos cambios temporales en una rama, hay un comando que es otra magia de git:
- git stash branch nameBranch -> Este comando crea la rama nameBranch y le asigna los cambios stasheados 
Si tienes cambio no esenciales y stasheas los cambios lo mejor es que pongas en memoria temporal estos y en caso de no funcionar eliminalos, asi como sigue:
- git stash drop -> Elimina los cambios almacenados en memoria temporal (stash)

### Git Clean: limpiar el proyecto de archivos no deseados

En caso de tener copias no deseadas de un mismo o varios archivos este comando nos ayudara a discrepar los que sirven de los que no, entonces:
- git clean --dry-run -> nos mostrara un listado de los archivo que seran limpiados del proyecto.
Pero para ejecutarlo hace falta algo mas:
- git clean -f -> borrara los archivos
- git clean -df -> borrara las carpetas no trackeadas
### Git Cherry pick
Este nos trae commit viejos al head de un branch.
- git cherry-pick idCommit -> Esto nos trae el commit del ID a la rama master
Ojo: Esta es una mala practica pero se puede usar para cambiar el head de cualquier rama
### Git Reset y Reflog
El comando reflog lo que hace es mostrarnos todos los cambios en los diferentes HEAD's que pasaron por el tiempo, asi que:
- git reflog -> lista los HEAD's
Y cuando queramos traer algun head especifico:
- git reset HEAD(4) -> traera a staging esos cambios referentes al HEAD
- git reset --hard idHead -> Con esto todo vuelve a la normalidad!, pero borro lo posterior a este commit
### Git con amend
Este comando reconstruye commit de una manera muy util, si tienes un commit y recuerdas que no hiciste algo que era necesario o parte del commit vuelves haces los cambios los guardas y los agregas con add -A o "." luego haces git commit --amend (Remendar), este unira estos ultimos cambios con el ultimo commit.
- git commit --amend -> agrega los cambios al ultimo commit y te envia a registrar el comentario por si lo requires, no muestra nada mas que el commit.
### Git Grep y log
- git grep color -> muestra las palabras en el proyecto
- git grep -n color -> muestra la palabra con la ruta
- git grep -c la -> muestra el archivo y la cantidad de veces que usaste la palabra en el archivo
- git grep -c "<p>" -> busca etiquetas en el codigo
- git grepo -S cabecera -> Muestra todo lo que tenga que ver con la palabra incluso branchs commit o lo que sea

### Comandos y recursos
- git shortlog -sn -> muestra cuantos commit hicieron los miembros del proyecto
- git shortlog -sn --all -> Muestra todos los commit incluso los que fueron borrados
- git shortlog -sn --all --no-merge -> Commit sin merges
- git config --global alias.stats "shortlog -sn --all --no-merge" -> Agrega el alias
 - git blame archivo.html -> muestra a detalle los cambios en el archivo
 - git blame -c -> muestra a detalle los cambios en el proyecto
 - git command --help -> abre la documentacion local sobre el comando y su uso
 - git blame path/archivo.css -L35,53 -c -> este comando nos muestra quien modifico que en el archivo desde la linea 35 a la 53
 - git branch -r -> muestra las ramas remotas
 - git branch -a -> muestra todas las ramas
 Adionalmente Github puede mostrar personas contribuidores, modifcaciones issues resolve fixes entre otros y grafica geniales para enter adicion o eliminacion de codigo en varios tiempos y esto en insight.
 
### Resumen de lo aprendido
- git clone url -> clona la versión master o main del repositorio
- git add -> Prepara los cambios del directorio a la preparación o Staging
- git commit -> Envía los cambios al repositorio local
- git push -> Envía los cambios al repositorio remoto
- git fetch -> Trae los últimos cambios
- git merge -> Combina cambios entre ramas
- git pull -> Fusiona fetch y merge en el repositorio local

### Ramas o Branch’s
- git branch newBranch -> crea la nueva rama
- git checkout nameBranch -> cambia de rama
- git merge nameBranch -> combina la rama local con la del parametro
- git remote add origin URL -> direcciona el repositorio a un repositorio de servidor
- git remote -v -> muestra los repositorios donde seran enviados los cambios
- git push origin main -> empuja los cambios al repositorio
- git pull origin nameBranch -> combina las ramas a la local
- git pull origin main --allow-unrelated-histories -> combina las ramas con README o archivos creados por defecto en el repositorio
 
 Y todo esto gracias al curso de Git y Github Profesional de Platzi!, totalmente recomendable.
