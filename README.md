Practica 1
==========
<pre>
Autor: Francisco Valverde Villalba
Licencia: GPL v3
</pre>
En este documento hablo sobre el despliegue de una aplicación PHP, en el PaaS llamado OpenShift de RedHat. Concretamente mi practica se basa en un periodico digital el cual funciona en lenguaje PHP y apoyandose en una base de datos con la que nos conectamos a ella por mySQL.

Registro (OpenShift)
--------------------
Los pasos para crear y desplegar dicha aplicación en OpenShift:

* <strong>Registrar la aplicación en la interfaz web de OpenShift</strong>

Para registrar la nueva aplicación pulsamos en add application una vez registrados. En la ventana que se nos abre buscamos el tipo de aplicación que vamos a crear, en mi caso PHP 5.3 (PHP es un lenguaje de scripting del lado del servidor de propósito general originalmente diseñado para el desarrollo web para crear páginas web dinámicas.).

Indicamos la dirección publica URL que será: <i>http://periodico-franvalverdeP1.rhcloud.com</i>

* <strong>Agregar Utilidades</strong>

Agregamos otros instrumentos necesarios para que nuestro periodico funcione correctamente. En primer lugar añadimos mySQL 5.1 y posteriormente phpmyadmin, si no se tiene instalado mySQL no se podrá instalar phpmyadmin.

Desde la interfaz web podemos clickar en la seccion de add database mysql y continuamos con el asistente.

Para phpmyadmin (una vez que se tiene instalado mysql) pulsamos en add tool y elegimos phpymadmin 4.0 y continuamos con el asistente.

<i> Es importante anotar los datos de autentificación que nos facilita openShift cuando agregamos tanto mySql como phpmyadmin. En ellos da información para conectarnos via web o via rhc.</i>


Conexión a BD (Terminal Ubuntu)
-------------------------------

Para poder acceder a phpmyadmin necesitamos realizar una configuración previa, en caso de no hacerlo nos motrará el error 2002 de mysql.

* Instalamos rhc:
<pre>
sudo apt-get install rubygems
sudo gem install rhc
</pre>
* Configuramos rhc:
<pre>
rhc setup
//introducimos usuario y contraseña de openshit
//creamos token y generamos llave publica de ssh
</pre>

* Conectarnos por ssh

En el portal web aparece en el lateral derecho un dirección con la cual podemos acceder por ssh: <i>ssh 5263....@periodico-franvalverdep1.rhcloud.com</i>. 
Desde la linea de comandos la escribimos y accederemos a nuestra aplicación via ssh. Lo siguiente sera poner la siguiente orden con la cual ya si nos dejará acceder desde phpadmin a mysql.
<pre>
env | grep OPENSHIFT
</pre>

Añadiendo BD (phpmyadmin)
-------------------------

Para acceder solo hay que pulsar al enlace que tenemos en el panel de configuración de openshift e intrudir el usuario y contraseña que nos facilita mysql.
Una vez dentro creamos tres tablas que contendran los comentarios, las noticias y los usuarios.

<img src="http://s2.subirimagenes.com/imagen/previo/thump_8663891myadmin.png">

Copia local (git)
-----------------


