# Guía HOW TO 

----------

## Comandos Linux para manejo Servidores
### Servidor Web Apache

----------



#### 1.- ¿Cómo sabemos si tenemos conexión a internet? Pista: ifconfig, ping.	
1. **¿Qué hace el comando?**
	<p><u>ifconfig</u>:muestra interfaces de red(ip,mascaras de subred...).<br>
	<u>ping</u>:determina la conectividad de red entre una fuente y un dispositivo. 
1. **¿Cómo se usa?**
	<p><u>ifconfig</u>: ifconfig.<br>
	<u>ping</u>: ping -c 4 hostinger.es donde -c 4 corresponde al níumero de paquetes que enviamos al servidor 	
1. **¿Por qué responde a la pregunta?**
	<p>Porque sabremos si tenemos conexión a internet mediante el envío y recepción de paquetes de datos a un servidor. 	
1. **¿Cómo se interpreta la salida?**
	<p>Se han enviado 4 paquetes de datos y se han recibido esos mismos paquetes de datos del servidor sin perdida de información por lo que hay conexión a correcta a internet.
	

----------

#### 2.- ¿Cómo sabemos si nuestro servidor es accesible desde Internet? Pista: ufw, netstat.

1. **¿Qué hace el comando?**
	<p><u>ufw</u>:nos permite interactuar con nuestro firewall(añadir reglas de filtrado,ver el estado...).<br>
	<u>netstat</u>:nos ofrece información acerca de nuestra red(estado de puertos con su ip y ptocolo...). 
1. **¿Cómo se usa?**
	<p><u>ufw</u>:ufw status para ver el estado/sudo ufw 80/tcp para permitir trafico en este puerto y su protocolo.<br>
	<u>netstat</u>:netstat -ano para ver el estado de puertos. 
1. **¿Por qué responde a la pregunta?**
	<p>Porque el puerto 80 que es el utilizado por servidores web está escuchando y listo para el intercambio de información.Sí teclemaos desde otro pc la ip de nuestro servidor veremos que carga la página de inicio de nuestro servidor.
1. **¿Cómo se interpreta la salida?**
	<p>Se ha añadido regla en el firewall para permitir intercambio de información en el puerto 80 y además como se puede ver con netsat dicho puerto está escuchando y listo.
	 
----------

#### 3.- ¿Cómo sabemos a quién pertenece una dirección web (URL)? Pista: dig, nslookup.	
1. **¿Qué hace el comando?**
	<p>Ambos permiten averiguar la ip de una url o viceversa. 
1. **¿Cómo se usa?**
	<p><u>dig</u>:dig hostinger.es +short para delimitar la salida.<br>
	<u>nslookup</u>:nslookup hostinger.es. 
1. **¿Por qué responde a la pregunta?**
	<p>Porque se nos da información de a quien pertenece una url 
1. **¿Cómo se interpreta la salida?**
	<p> Ambos proporcionan la ip del dominio o url introducida. 

----------
 
#### 4.- ¿Cómo probamos que podemos acceder a un servidor? Pista: curl, wget.	
1. **¿Qué hace el comando?**
	<p><u>curl</u>:permite comprobar la conectividad a una url.Podemos mostrar el contenido de una página en html.<br>
	<u>wget</u>:también permite comprobar la conectividad a una url y realizar descargas de ella.
1. **¿Cómo se usa?**
	<p><u>wget</u>: wget https://wordpress.org/latest.zip<br>
	<u>curl</u>: curl hostinger.es	
1. **¿Por qué responde a la pregunta?**
	<p>Por que al poder realizar una descarga correcta de un servidor muestra que la conectividad a el es correcta. 	
1. **¿Cómo se interpreta la salida?**
	<p>Con wget hemos realizado la descarga del recurso solicitado a nuestro directorio de trabajo. Por otro lado mediante curl y la página web indicada se nos muestra dicha página en formato HTML.

----------

#### 5.- ¿Qué otros comandos te han hecho falta?	
1. **sudo su**
	<p> Para trabajar en consolo como super usuario. Se pide contraseña.
1. **clear**
	<p> Limpia la consola o terminal.
1. **nc o netcat**
	<p> Se puede probar la conectividad a una ip y puerto que indiquemos. Si tecleamos nc -zv 192.168.1.44 80 observamos una salida connection succeeded¡. Indica que la conexión al puerto 80 de nuestra ip es satisfactoria.	
1. **sudo apt update**
	<p>Actualizaciones disponibles.
1. **sudo apt upgrade**
	<p>Instalación de actualizaciones disponibles.