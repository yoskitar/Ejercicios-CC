# Tema 3: Microservicios

## Ejercicio 1.- Realizar una aplicación básica que use express para devolver alguna estructura de datos del modelo que se viene usando en el curso.
Como ejemplo ilustraremos la realizada en el curso de [**TDD**](https://github.com/Miguel-y-Oscar/Geolocalizaciones-de-medios-sociales/blob/master/src/app.js):

![NVM instalado](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/express-app.png)

En ésta, importamos el módulo **express** y creamos un servidor con la función `express()`, que iniciaremos en el puerto indicado con el método `listen()`.

## Ejercicio 2.- Programar un microservicio en express (o el lenguaje y marco elegido) que incluya variables como en el caso anterior.
Partiendo de la aplicación anterior, nos centraremos en una de las rutas definidas, en la que hacemos uso de **parámetros** para obtener los **post** que **contengan** el **hastag** pasado como parámetro en la ruta:

![NVM instalado](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/express-param.png)

## Ejercicio 3.- Crear pruebas para las diferentes rutas de la aplicación.
Para este caso, hemos definido diversos tipos de test:

![NVM instalado](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/express-test.png)

* El primero que podemos observar se trata de un **test unitario** que nos permite testear el funcionamiento de las clases post y tag. Para ello hacemos uso de la función `expect()` del módulo **Chai**.

* Los otros dos test definidos son denominados **test de integración**, y nos permitirán **testear** en nuestro caso las **rutas** definidas en nuestra aplicación **express**. En este caso deberemos **importar** el **módulo app**, que previamente deberemos de exportar del fichero 'app.js' empleando `module.exports=app`. Para estos test haremos uso del módulo **supertest**, que nos permite testear las rutas definidas, sin necesidad de previamente ejecutar una instancia de la aplicación.

## Ejercicio 5.- Usar rake, invoke o la herramienta equivalente en tu lenguaje de programación para programar diferentes tareas que se puedan lanzar fácilmente desde la línea de órdenes.
En nuestro caso, haremos uso de 'npm' para la ejecución de las diferentes tareas definidas en el archivo **package.json** dentro del apartado de scripts:

![NVM instalado](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/npm-scripts.png)