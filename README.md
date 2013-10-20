Practica 1
==========
<pre>
Autor: Francisco Valverde Villalba
Licencia: GPL v3
</pre>
En este documento hablo sobre el despliegue de una aplicación PHP, en el PaaS llamado OpenShift de RedHat. Concretamente mi practica se basa en un periodico digital el cual funciona en lenguaje PHP y apoyandose en una base de datos con la que nos conectamos a ella por mySQL.

Pasos en OpenShift
------------------
Los pasos para crear y desplegar dicha aplicación en OpenShift:

* <strong>Registrar la aplicación en la interfaz web de OpenShift</strong>

Para registrar la nueva aplicación pulsamos en add application una vez registrados. En la ventana que se nos abre buscamos el tipo de aplicación que vamos a crear, en mi caso PHP 5.3 (PHP es un lenguaje de scripting del lado del servidor de propósito general originalmente diseñado para el desarrollo web para crear páginas web dinámicas.).

Indicamos la dirección publica URL que será: <i>http://periodico-franvalverdeP1.rhcloud.com</i>

* <strong>Agregar Utilidades</strong>

Agregamos otros instrumentos necesarios para que nuestro periodico funcione correctamente. En primer lugar añadimos mySQL 5.1 y posteriormente phpmyadmin, si no se tiene instalado mySQL no se podrá instalar phpmyadmin.

Desde la interfaz web podemos clickar en la seccion de add database mysql y continuamos con el asistente.

Para phpmyadmin (una vez que se tiene instalado mysql) pulsamos en add tool y elegimos phpymadmin 4.0 y continuamos con el asistente.

