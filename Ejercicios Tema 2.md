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
