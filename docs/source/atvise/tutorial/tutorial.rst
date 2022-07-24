********
Tutorial 
********
El objetivo principal del este tutorial es familiarizar al usuario con el proceso de ingeniería detrás del uso de un sistema SCADA.

En este tutorial se muestran ejemplos base, para el uso correcto del sistema SCADA.

Iniciando el sistema
====================
.. hint::
  Si se tiene alguna consulta adicional con respecto a la instalación o a las licencias, contacte con el siguiente correo:
  soporte@vestersl.com

1. Dar click derecho en el icono de atvise en la esquina inferior derecha del escritorio en la barra de tareas.
2. Se le da click al botón de ``License`` en el menú que se despliega.
3. Se introduce el código de licencia que se encuentra en el correo que manda atvise para la licencia de prueba.

.. image:: img/StartingAdvice.PNG

.. attention:: 
  El icono de atvise se pone verde, lo que significa que el servidor se encuentra arriba y listo para ser utilizado.
  Si es de otra manera no es posible conectarse al servidor.

.. hint:: 
  El protocolo de red que utiliza el servidor de atvise es OPC UA por el puerto 4840.
  Por lo anterior, es importante revisar que ninguna otra aplicación utilice este puerto de red. 

.. tip:: 
  Es posible apagar el servidor atvise escogiendo la opción ``Stop Server`` del mismo menú mencionado anteriormente.


Conectando con el constructor de atvise
=======================================

El constructor de atvise es la herramienta de ingeniería que se utiliza para desarrollar proyectos en SCADA. 
El mismo permite, manejar variables, objetos, grupos y usuarios, así como mostrar en pantalla las figuras configuradas, entre otras cosas.

Iniciando el constructor
------------------------
1. Se le da click derecho al icono de atvise en el taskbar, además se abre ``Project Console`` y dentro se le da click a la opción ``Builder`` para abrir el constructor de atvise.

.. image:: img/builder.PNG

Conectando con el servidor
--------------------------

Después de haber iniciado el constructor siguiendo los pasos anteriores, se abre una ventana la cual pregunta por el servidor al que se quiere conectar, el usuario y la contraseña.
Lo anterior es el sistema que tiene atvise para conectar al modulo OPC UA en la máquina cliente.
La dirección IP por default que usa el servidor es el LocalHost.

.. hint::
  ``root`` es el usuario por defecto del sistema en cada nuevo proyecto. 
  Si se desea agregar una contraseña u otro usuario, se utiliza la herramienta de ``User Management``.

.. image:: img/user.PNG


1. Seleccione ``builder -> Connect to server`` de la barra de tareas.
2. Una vez que se abre la ventana de conexión, se agregan los datos pertinentes al usuario y la dirección al servidor que se desea conectar. 

.. hint:: 
  Es posible ingresar la dirección IP de algún otro servidor o de algún equipo en la red local.

3. Hecho lo anterior, se presiona ``OK`` en la caja de dialo y se procede a conectar. 

.. image:: img/server.PNG

Creando la primer pantalla en atvise
====================================

Ahora que ya se cubrieron las bases de cómo conectarse al atvise. Esta sección busca dar la introduccion a cómo interactuar con el constructor de atvise.
De manera que en esta parte se va a añadir una pantalla base.

Añadiendo un display al proyecto
--------------------------------

1. Abra la ruta ``Servers -> My Server -> Display`` y de clicl derecho en el folder llamado ``MAIN``.
2. Escoja la opción ``Add Display`` de la lista desplegada.
3. Escriba un nombre apropiado para el display en cuestión.
4. Hechos los pasos anteriores se le da click a ``OK``.

.. image:: img/display.PNG


Editando el display y añadiendo eventos
---------------------------------------

1. Dar doble click en el display se que acaba de crear, para abrir el editor gráfico del display.
2. Busque el signo del rectángulo y selecciónelo.  
3. En el canvas blanco, haga un rectángulo.
4. Por último es necesario darle click al signo del CD para guardar la modificación.

.. image:: img/editor.PNG

.. hint:: 
  Es posible usar la rueda del mouse para hacer zoom.


Visualizando el display en la web
---------------------------------

1. Ahora para observar el display que se ha creado en el tutorial, se abre el browser de internet de preferencia. 
2. Ponga en la barra de búsqueda el URL asignado al ``LocalHost``, normalmente es el siguiente : "https://127.0.0.1/"
3. Abra el display dando click al nombre que se asignó en la barra gris de la derecha. 

.. attention:: 
  Si se hacen cambios al display una vez que se abrió en el browser, utilice la tecla ``F5`` para recargar la página. 

Creando displays dinámicos
==========================

Primeras dinámicas
------------------

En esta sección se van a cambiar algunas de las propiedades gráficas de diferentes elementos dependiendo del valor que tengan cieras variables de datos.

Añadiendo variables de datos al proyecto
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Para añadir variables de datos al proyecto, dele click en la pestaña de ``Objects`` en la barra izquierda de la interfaz del constructor.

Se van a añadir 3 variables para este ejemplo:

* "testString" del tipo "String"
* "testBool" del tipo "Boolean"
* "testInt" del tipo "Int16"

1. Dar click derecho en la siguiente ruta ``Servers -> My Server -> Objects`` y abrir el folder.
2. Escoja ``Add Node -> Data Variable`` del menú que aparece.
3. Escoja ``String`` de la lista de tipos de variables.
4. Escriba el nombre de la variable, es este caso "testString" y seleccione la casilla `OK`.
5. Repita para las otras dos variables de la misma forma, pero seleccionando los tipos respectivos. 

.. image:: img/Dinamic.PNG

Leyendo y cambiando los valores de las variables de datos
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""

Hecho todo lo anterior, usted verá una lista de variables para cada una de ellas que se agregó en la sección anterior.
Si por alguna razón fuera necesario cambiar el valor de alguna de las variables se deben seguir los siguientes pasos:

1. Dar doble click en la entrada de la variable llamada ``testString`` para que se abra una ventana de detalle para esa variable.
2. Ahora se le da doble click en la columna de ``AttributeValue`` en la file de ``Value`` para editar el valor de la variable en cuestión.

.. image:: img/value.PNG


Usando los controles predeterminados de atvise
==============================================

Control de Barras
-----------------

1. Haga un display nuevo siguiendo las instrucciones anteriores.
2. En la parte baja del editor gráfico hay una barra con varios controles, agarre y suelte uno en el canvas de dibujo. 
3. Al hacer lo anterior, aparece una lista de parámetros del lado derecho. Seleccione la variable "testInt".
4. Puede cambiar otros parámetros si lo desea.  

.. image:: img/barcontrol.PNG

Control Incremental
-------------------

1. Ahora agarre y suelte un ``Button Increment/Decrement`` al canvas de dibujo.
2. Seleccione la variable "testInt". 
3. Seleccione "10" como el valor de salto. Hecho esto la variable incrementará su valor en 10 cada vez que se presione el botón.

.. image:: img/incrementcontrol.PNG


Conectando a un servidor externo
================================

Esta sección muestra como añadir un servidor externo al sistema.

Inicializando un servidor OPC UA de prueba
------------------------------------------
Primero que nada es importante iniciar el servidor de prueba y para esto es importante importar una estructura de datos.

Dentro de la jerarquía de archivos generada al instalar el programa, dentro de la carpeta ``atvise -> Tools -> OPC UA testserver`` y corra ese ejecutable.

Añadiendo un servidor externo
-----------------------------

1. Abra la carpeta ``Servers -> My Server -> Data Sources`` y de click derecho en ``Data Sources``.
2. Escoja ``Add Data Source`` and then ``OpcUa`` para abrir el menú de configuración de la fuente de datos. 
3. El servidor de prueba corre en el puerto 4841, entonces para acceder al mismo se utiliza la siguiente ruta: ``opc.tcp://localhost:4841`` 

Navegando en el servidor externo
--------------------------------

1. De click en la nueva instancia de servidor, en la lista de servidores.
2. Escoja la opción ``Browse``.

.. hint:: 
  Navegar por un servidor externo es sumamente útil para copiar rutas, identificadores de diferentes nodos y copiar variables de datos. 


Ingeniería  orientada a objetos
===============================
Con el fin de introducir el concepto de ingeniería orientada a objetos, se desarrolla un ejemplo el cual tiene como objetivo diseñar un ``Type`` encargado de mostrar y controlar el estado de una luz eléctrica en un edificio. 

Para este experimento se manejan las siguientes variables: 

* Intensidad Luminosa.
* Alarma de protección.

.. hint::
  Navegando por el servidor de prueba se pueden hallar estas variables.
  Si quiere puede copiarlas.

Agregando un nuevo tipo de objeto
---------------------------------
1. Dar click derecho en el botón de ``Object Types`` en el árbol de archivos.
2. Seleccione ``Add Note -> Object Type``.
3. En el menú que aparece, se puede escribir el nombre del nuevo tipo de variable, en este caso se usa ``Light``.
4. Después de darle ``OK``, aparece el nuevo tipo ``Light`` en la lista de tipos.

.. image:: img/type.PNG

Agregando una estructura de datos
---------------------------------

1. Dar click derecho al tipo creado anteriormente ``Light``.
2. Escoja ``Add Node -> Folder`` del menú que aparece.
3. Escoja un nombre representativo para el folder en cuestión como ``ALARMS`` y agreguelo al tipo ``Light``.
4. Repita el paso anterior pero ahora cree otro folder con el nombre ``COMMANDS``.
5. Nuevamente reporta el paso 3 pero haga otro folder con el nombre ``SIGNALS``. 

.. image:: img/struct.PNG

Creando instancias de objetos
-----------------------------
En esta sección se crean instancias del tipo de objeto creado anteriormente.

1. Dar click derecho en ``Servers -> My Server -> Objects`` y escoja ``Add Node -> Object``. en el submenú que aparece, usted verá que aparece el tipo ``Light``, dele click para crear una instancia de este tipo.
2. El objetivo es crear cinco instancias numeradas, por esto se le da click a la opción de ``numbered``.
3. Con el fin de usar nombres claros, se remplaza el nombre por defecto por ``OfficeLight_%1`` , el ``%1`` es un comodín, el cual será remplazado por ``001-005`` por cada una de las instancias.
4. El object count se pone en 5, ya que se quieren cinco instancias.  

.. image:: img/instance.PNG






