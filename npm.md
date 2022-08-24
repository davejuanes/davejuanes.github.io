## Gestión de dependencias y paquetes con NPM
Node package modules, este gestor de paquetes nos ayuda a poder gestionar los recursos en nuestros proyectos con NODE, algunas de las buenas practicas son definir por defecto los comandos:
- git init Inicializar el repositorio GIT
- git npm Genera los datos generales de nuestro proyecto

### Instalación
NPM por defecto se instala junto a NODE (Sitio oficial)[https://nodejs.org/es/], lo mas recomendable es realizar una instalación de la version LTS (Long Time Support).

### Gestión e instalación de paquetes
Por defecto NPM utiliza la carpeta ```node_modules``` aqui es donde se alojan todos los recursos donde se listan los componentes, ojo esta carpeta no debe ser enviada a ningun repositorio (utilizar .gitignore)
- npm install moment --save-dev  --save significa que es necesario para producción --save-dev se utiliza solo para ambientes de desarrollo
- npm install date-fns --save-dev
- npm i date-fns -D se instala y como una dependencia de desarrollo i es un shortcut de install
- npm i moment -S se guarda como parte del proyecto
- npm i -g nodemon instala de manera global en caso de ser necesario se debe usar sudo en linux y mac en windows con privilegios de instalación
- npm list -g --depth 0 Lista los paquetes instalados de forma global
- npm install eslint -O Instalación opcional
- npm fund Significa que el paquete requiere financiamiento para apoyar a los desarrolladores.
Otros comandos utliles son:
- npm install react --dry-run Simula que instala el paquete
- npm install webpack -force o -f Esto forza la instalación desde la instalación ultima que existe (Se debe revisar en que sección se encuentra)
- npm install Este comando revisa el archivo package y las vuelve a instalar todo lo que se encuentre ahí
- npm install json-server@0.15.0 Este comando instala la versión especifica

## Como actualizar paquetes
- npm list Nos lista todos los paquetes instalados
- npm outdate Esto ve que paquetes necesitan o tiene una actualización
- npm outdate --d Esto ve que sucede la interacción con tu maquina y los servidores de los paquetes
- npm update Esto actualiza todos los paquetes a la ultima versión
- npm install json-server@latest Esto instala la ultima versión de este paquete
- npm uninstall json-server Elimina lo que instalo este paquete dentro del proyecto
- npm uninstall webpack --no-save Elimina todo de node_modules pero no de package
## Versionado del archivo package.json
Dentro del archivo package.json controlamos ^ (caret) para decir que podemos actualizar la versión del paquete, en el caso de no querer usar el caret definiremos un version fija.
![Imagen de versiones](https://static.platzi.com/media/user_upload/wheelbarrel-no-tilde-caret-white-bg-w1000-72ca1a72-4c7f-4abe-8482-425c01a72f89.jpg)
### Scripts
Dentro del archivo package.json encontramos una sección ```"scripts":``` aqui podemos definir script que realizen determinadas funciones en el proyecto.
Practicamente si registramos un script correra comandos dentro del proyecto:
```
"deploy": "npm run format && npm run build",
"hola": "node"
```
El modo de ejecución es
- npm run script
- npm run deploy
- npm run hola
- npm test Ejecuta los test que tengamos registrados dentro de esta sección
- npm start Inicia el proyecto ejecuta los elementos

## Errores en la gestión de NPM
Dentro del uso de NPM podemos encontrarnos con errores comunes que tienen soluciones faciles y complicadas, para esto se tiene que primero habilitar el modo ```verbose```
- npm run build--dd Habilita el modo verbose Muestra todo lo que esta sucediendo en el proyecto
Este comando nos permitirá identificar la ubicación de nuestro typo o error que nos presenta el paquete y por asi poder solucionar.

## Cache
El comando para eliminar la cache es:
- npm cache clean --force Elimina el cache del sistema
- npm cache verify Verifica que no haya temporales en el sistema
- rm -rf node_modules/ Este comando elimina la carpeta definida
- sudo npm install -g rimraf Instala un paquete para poder borrar la carpeta node_modules
- rimraf node_modules Elimina la carpeta con el paquete rimraf

## Gestión de seguridad en proyectos con NPM
Dentro de todo proeycto se debe gestionar bajo estandares pero con NPM podemos hacerlo de una manera eficiente.
Luego de ejecutar npm install NPM nos muestra si hay alguna vulnerabilidad, se usa el comando npm audit
- npm audit Nos muestra datos de paquetes
- npm audit --json Genera la información en formato JSON
- npm update eslint-utils --depth 2 Actualiza el paquete
- npm audit fix Nos garantiza que todos los datos son seguros dentro del proyecto




