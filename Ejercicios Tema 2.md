# Tema 2: Desarrollo basado en pruebas

## Ejercicio 1.- Instalar alguno de los entornos virtuales de node.js (o de cualquier otro lenguaje con el que se esté familiarizado) y, con ellos, instalar la última versión existente, la versión minor más actual de la 4.x y lo mismo para la 0.11 o alguna impar (de desarrollo).

En nuestro caso instalaremos **nvm**, uno de los entornos que se proporcionan en el [temario](http://jj.github.io/CC/documentos/temas/Desarrollo_basado_en_pruebas.html) para el lenguaje Node Js. Para realizar todo el proceso, seguiremos los pasos tal como se indica en su [repositorio](https://github.com/nvm-sh/nvm) GitHub.

### Instalación
Ejecutamos el siguiente comando para la instalación del entorno virtual nvm.
~~~
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh | bash
~~~
![NVM instalado](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm_installed.png)
### Uso de nvm
Con el siguiente comando, se instala automáticamente la última versión existente:
~~~
nvm install node
~~~
![NVM instlar lv](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm_node_lv.png)

![NVM use node](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm_use_node_lv.png)

Podemos emplear el siguiente comando para conocer una lista de las diferentes versiones que podremos instalar con el anterior comando:
~~~
nvm ls-remote
~~~
![NVM versiones](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm_version_4_Lminor.png)

Si queremos especificar la versión a instalar, empleamos la siguiente orden:
~~~
nvm install <x.x.x> #<major,minor,path>
~~~
![NVM instalar versiones](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm-install-versions.png)

![NVM run node version](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/nvm_run_version.png)

## Ejercicio 2.- Crear una descripción del módulo usando package.json. En caso de que se trate de otro lenguaje, usar el método correspondiente.
Ilustraremos el ejercicios con dos ejemplo realizados. El primero se corresponde con un proyecto personal desarrollado:

![Package.json](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/package_json.png)

EL segundo ejemplo se corresponde con el package.json definido para el [curso realizado de TDD](https://github.com/Miguel-y-Oscar/Geolocalizaciones-de-medios-sociales):

![Package.json GeoTag](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/package_json_geotag.png)

En estos ejemplos observamos como se definen las dependencias externas de nuestro proyecto que serán necesarias de instalar para que nuestro servicio pueda funcionar adecuadamente como se espera. Además nos permite definir una serie de ordenes en la sección 'scripts', que ejecutará los comandos que le indiquemos cuando dicho script sea llamado, por ejemplo 'npm test' que ejecutará los comandos definidos 'npx nyc --reporter=lcov nyc --reporter=lcov mocha && npx codecov'.

## Ejercicio 4.- Para la aplicación que se está haciendo, escribir una serie de aserciones y probar que efectivamente no fallan. Añadir tests para una nueva funcionalidad, probar que falla y escribir el código para que no lo haga. A continuación, ejecutarlos desde mocha (u otro módulo de test de alto nivel), usando descripciones del test y del grupo de test de forma correcta. Si hasta ahora no has subido el código que has venido realizando a GitHub, es el momento de hacerlo, porque lo vamos a necesitar un poco más adelante.
Para el microservicio que nos encontramos desarrollando, hemos definido los siguientes casos de test entre otros muchos. En los ilustrados, se comprueba concretamente que las mutaciones fallen atendiendo a un mal número de argumentos de entrada o salida y tipos correspondientes. Para ello estamos empleando mocha conjuntamente con un paquete de test llamado [easygraphql-tester](https://easygraphql.com/docs/easygraphql-tester/usage) que nos permite realizar las asserciones.

![Test](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/tests.png)

El segundo ejemplo que se muestra a continuación es el desarrollado para el proyecto [GeoTag](https://github.com/Miguel-y-Oscar/Geolocalizaciones-de-medios-sociales).

![Test GeoTag](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/tests_geotag.png)

Estas herramientas nos permiten comprobar el correcto funcionamiento de las funciones o clases definidas, permitiendonos realizar unas buenas prácticas mediante lo que se conoce como programación defensiva, y poder testear tanto el buen funcionamiento, como el erróneo, devolviendose estados de error cuando efectivamente deben de darse.

## Ejercicio 5.- Darse de alta en un servicio de integración continua. Muchos están conectados con GitHub por lo que puedes usar directamente el usuario ahí, a través de un proceso de autorización, acceder al contenido e incluso informar del resultado de los tests. Activar el repositorio en el que se vaya a aplicar la integración continua. Travis permite hacerlo directamente desde tu configuración; en otros se dan de alta desde la web de GitHub. Crear un fichero de configuración para que se ejecute la integración y añadirlo al repositorio.
Integración de [travisCI](https://travis-ci.org/) con el repositorio y autorización de usuario:

![TravisCI](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/travisCI.png)

![WebHook](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/webhook.png)

Contenido del fichero de configuración para integración continua, donde especificacmos desde el lenguaje, como las versiones del lenguaje con las que ejecutaremos los tests elaborados, indicando el script a ejecutar, que en nuestro caso es npm test, donde test se encuentra definido en el package.json como una serie de comandos a ejecutar para ejecutar nuestros test. Previo a ello, será necesario instalar las dependencias de nuestro proyecto para que se ejecute correctamente, indicado con la orden npm install.

![Travis.yml](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/travis_yml.png)


