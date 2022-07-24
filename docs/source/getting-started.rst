Primeros pasos
==============

Este ambiente de desarrollo está orientado a correr en cualquier plataforma
en donde contenedores de Linux sean soportados, pero ha sido principalmente
probado en hosts de Ubuntu.

Requisitos
----------
* **Vagrant** para controlar el ambiente de desarrollo, por favor siga las
  `instrucciones de instalación para su plataforma aquí <https://www.vagrantup.com/downloads.html>`_.
* **Docker** para proveer un ambiente liviano basado en contenedores para vagrant.
  Por favor siga las `instrucciones de instalación para su plataforma <https://docs.docker.com/install/>`_.
* **Git** cliente para clonar el repositorio

Clonar e Iniciar
----------------

Clone el repositorio de GitHub, luego inicie el ambiente de vagrant

.. code-block:: bash

   git clone https://github.com/gabomora2200/DocsProyectoElectrico
   cd ie0417
   vagrant up

.. tip::

   Este proceso podría tomar un tiempo la primera vez, ya que Docker va a empezar
   a descargar la imagen del contenedor desde el registro público de Docker.

Una vez la máquina de Vagrant está arriba y corriendo, puede establecer una
conexión remota segura por ssh con `vagrant ssh` y la salida debe ser similar a:

.. code-block:: bash

  $ vagrant ssh
  Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.15.21-1-linux x86_64)

  $$$$$$\ $$$$$$$$\        $$$$$$\  $$\   $$\   $$\   $$$$$$$$\
  \_$$  _|$$  _____|      $$$ __$$\ $$ |  $$ |$$$$ |  \____$$  |
    $$ |  $$ |            $$$$\ $$ |$$ |  $$ |\_$$ |      $$  /
    $$ |  $$$$$\          $$\$$\$$ |$$$$$$$$ |  $$ |     $$  /
    $$ |  $$  __|         $$ \$$$$ |\_____$$ |  $$ |    $$  /
    $$ |  $$ |            $$ |\$$$ |      $$ |  $$ |   $$  /
  $$$$$$\ $$$$$$$$\       \$$$$$$  /      $$ |$$$$$$\ $$  /
  \______|\________|       \______/       \__|\______|\__/

        IE0417 development environment 22.03.0

  Last login: Mon Feb 28 04:26:37 2022 from 172.17.0.1
  dev@ie0417-devel:~/ws$

.. note::

   El vagrant está configurado para sincronizar algunos directorios desde su máquina
   host hacia su máquina de desarrollo, en especial el directorio con el repositorio
   de git está disponible en `~/ws` y es su directorio por defecto al hacer SSH.

.. tip::

   Usted puede abrir tantas sesiones SSH como quiera. Algunos editores de código
   como Visual Studio Code soportan `ssh remote edition <https://code.visualstudio.com/docs/remote/ssh>`_, lo cual es conveniente.

Ciclo de vida de la máquina de desarrollo
-----------------------------------------

Una vez haya terminado con su desarrollo, puede "apagar" el contenedor con `vagrant halt`.

Usted tambien podría destruir el ambiente completamente (por ejemplo para actualizar
a una version nueva del ambiente), puede hacerlo con `vagrant destroy`.

