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
