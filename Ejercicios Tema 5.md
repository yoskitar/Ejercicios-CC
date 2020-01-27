# creación y provisionamiento de máquinas virtuales

## Ejercicio 1.- Instalar una máquina virtual Debian usando Vagrant y conectar con ella.

Para ello ejecutamos el comando `vagrant init debian/stretch64`, lo que nos creará un vagrantfile con la configuración básica y la imagen indicada en el argumento. Tras esto, levantamos la máquina empleando `vagrant up`, y podremos conectarnos a ella empleando `vagrant ssh`.

![Vagrant up ](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/Vagrant_debian_up.png)


![Vagrant ssh ](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/Vagrant_debian_ssh.png)

## Ejercicio 3.- Crear un script para provisionar de forma básica una máquina virtual para el proyecto que se esté llevando a cabo en la asignatura.

El Script puede ser consultado en el siguiente enlace:
[Playbook provisionamiento gestión de productos](https://github.com/yoskitar/Cloud-Computing-CC/blob/master/provision/playbook_provision_gp.yml)

En este se realiza el pull de la imagen docker del ms subido a dockerhub, para poder realizar el provisionamiento de manera más fácil.

## Ejercicio 4.- Configurar tu máquina virtual usando `vagrant` con el provisionador ansible.

Para ello podremos hacer de dos formas, empleando desde la línea de comandos `ansible-playbook`, o bien, desde el vagrantfile, empleando la siguiente opción:

```
config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook_provision_gp.yml"
  end
```

Con esto indicamos a vagrant que realice el provisionamiento cuando se realice `vagrant up`, empleando ansible, y utilizando el playbook indicado entre comillas.

Puede consultar el [fichero completo](https://github.com/yoskitar/Cloud-Computing-CC/blob/master/provision/Vagrantfile) si desea más información.

## Ejercicio 5.- Desplegar la aplicación de cualquier otra asignatura donde se tenga ya el código fuente con todos los módulos necesarios usando un playbook de Ansible.

En este caso ilustraremos con la misma aplicación que estamos desarrollando. Realizamos todo el proceso anterior descrito, definiendo primeramente el vagrantfile, seguido de los playbooks y unos fichero de configuración donde espicificamos la configuración para unos grupos de hosts definidos. Al ejecutar vagrantfile, el servicio se encontrará accesible mediante los puertos 8080 y 8000.

![Vagrant ssh ](https://raw.githubusercontent.com/yoskitar/Ejercicios-CC/master/imagenes/vagrant_deploy_docker_ps.png)

El playbook definido para ello se encargará de comprobar que el servicio de MongoDB se encuentra levantado, y ejecutar los contenedores docker provisionados para cada uno de los micro-servicios. Puede consultar el fichero completo en el siguiente enlace:
[Playbook deploy](https://github.com/yoskitar/Cloud-Computing-CC/blob/master/provision/playbook_deploy.yml).

## Ejercicio 6.- Crear un rol common que haga ciertas tareas comunes que vayamos a usar en todas las máquinas virtuales de los microservicios de la asignatura (o, para el caso, cualquier otra asignatura).

Para respetar el principio de modularidad, se ha creado un playbook que contiene una serie de tareas de provisionamiento comunes y necesarias para el servicio completo. En este hemos incluido roles que nos permitirán configurar mongodb para ser utiliada como BD local, además de docker para poder decargar y ejecutar los contenedores de ambos micro-servicios.

Puede consultar el fichero para más información en el siguiente enlace:

[Playbook common](https://github.com/yoskitar/Cloud-Computing-CC/blob/master/provision/playbook_provision_common.yml).