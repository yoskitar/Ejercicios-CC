# Contenedores y cómo usarlos

## Ejercicio 2.- Tomar algún programa simple, “Hola mundo” impreso desde el intérprete de línea de órdenes, y comparar el tamaño de las imágenes de diferentes sistemas operativos base, Fedora, CentOS y Alpine, por ejemplo.
Creamos varios archivo [**Dockerfile**](https://github.com/yoskitar/Ejercicios-CC/tree/master/Recursos-Docker) empleando **diferentes imágenes base** e implementamos un **programa básico** que nos mostrará el mensaje "Hello Cloud Computing!" por pantalla. Para ello, una vez definida la aplicación, haremos uso de las **acciones**:
* `FROM`: Indicar la imagen y la versión que emplearemos de base en el contenedor.
* `RUN`: Ejecutar comandos como por ejemplo `apk install` para la instalación de paquetes necesarios que no vengan instalados por defectos con la imagen seleccionada.
* `WORKDIR`: Establecer el directorio de trabajo dentro del contendor.
* `COPY`: Copiar los archivos fuente a la ruta indicada.
* `CMD`: Para ejecutar las órdenes que deseamos, como es en este caso, lanzar la aplicación.

Una vez tenemos el dockerfile creado, podemos **construir** el contenedor a partir de éste empleando la siguiente orden:
```
sudo docker build -t yoskitar/cc-hello-docker-alpine .
```
Una vez creado, podemos **ejecutarlo** empleando la siguiente orden:

```
sudo docker run -it yoskitar/cc-hello-docker-fedora:latest
```
Con la opción `-it` nos permite ejecutar un **pseudo-terminal** (-t) en el contenedor en modo **interactivo** (-i).

Una vez creados los diversos contenedores a partir de los diferentes dockerfiles, con las diferentes imágenes de base, podemos **listar** los **contenedores** empleando `sudo docker images`.

Así, el tamaño de los contenedores creados anteriormente es el siguiente:

![Docker Images ](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/docker_images.png)

Como podemos comprobar, la imagen de **alpine** es la que **menor espacio** ocupa, en comparación con centos y fedora.

## Ejercicio 3.- Crear a partir del contenedor anterior una imagen persistente con commit.

Para ello hemos partido de la imagen del microservicio creado, y empleando el id del contenedor junto a la orden `docker commit` se ha creado la nueva imagen 'nuevo-gp', tal como se muestra a continuación:

![Docker Commit ](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/docker-commit.png)

## Ejercicio 7.-Reproducir los contenedores creados anteriormente usando un Dockerfile.
En nuestro caso, para la realización del ejercicio 2, creamos y ejecutamos cada uno de los contenedores empleando estos [dockerfiles](https://github.com/yoskitar/Ejercicios-CC/tree/master/Recursos-Docker).