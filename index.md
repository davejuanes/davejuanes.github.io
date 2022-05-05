## Dave Juanes

## Blog Personal

Soy Ingeniero de Sistemas con experiencia en tecnologias OpenSource durante 4 años, aquí podras encontrar mi experiencia con diferentes herramientas de software. Las tecnologias que utilizo y con las que mas experiencia tengo son:

- Laravel
- NodeJS
- ReactJS
- PostgreSQL

Entre algunas otras mas, espero que si estas aquí encuentres algo de utilidad, el contenido de este blog seran anotaciones recordatorios de uso y aplicacion de herramientas y librerias. 

### Git y Github
![Git y Github](https://camo.githubusercontent.com/38f113b96a368dfb7f634d2f2da97e7b8c748042d2a284b97c3fad048bb3ff55/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f323733322f312a6d74736b3366515f4252656d466964686b656c3364412e706e67)
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
- alias historia="git log --all --graph --decorate --online"

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

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/davejuanes/davejuanes.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
