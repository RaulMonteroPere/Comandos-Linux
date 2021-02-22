# Guía HOW TO 

----------

## Comandos Linux para instalación y configuración de Servidores y Java
### Servidor Web Apache, Tomcat, SSH, MaríaDB

----------



#### 1.- Instalación y configuración de JAVA.	
1. **¿Qué hace el comando?**,**¿Cómo se usa?**
	<p><u>apt-get  install default-jdk</u>:instala la última versión del jdk por defecto.<br>
	<u>java -version</u>:nos dirá si tenemos Java instalado y la versión. <br>
	<u>update-alternatives  --config  java</u>:para ver las diferentes instalaciones de java que tenemos y sus rutas, para configurar el JAVA_HOME.

1. **¿Por qué responde a la pregunta?**,**¿Cómo se interpreta la salida?**
	 
	<p>Al usar el java version observamos que la salida nos muestra que no hay Java instalado. Lo instalamos, y la salida nos muestra que se ha instalado java correctamente y posteriormente miramos si hay varias versiones de Java instalas para configurar el JAVA_HOME. En nuestro caso solo está instalada la de ahora mismo, por lo que no hay que hacer configuraciones.
	

----------

#### 2.- Instalación y configuración de APACHE.

1. **¿Qué hace el comando?**,**¿Cómo se usa?**
	<p><u>apt-get install apache2</u>:Este comando instalará Apache en nuestro PC<br>
	<u>systemctl status apache 2</u>: Con este comando vemos el estado del servicio de Apache. <br>
	<u>ufw status</u>:<br>estado del firewall,reglas creadas.<br>
	<u>ufw allow 80</u>:Apertura del puerto 80 en el firewall.<br>
	<u>ss -ltn</u>: puertos que están escuchando.	
1. **¿Por qué responde a la pregunta?**,**¿Cómo se interpreta la salida?**
	
 	<p> El comando de instalación procederá a instalar Apache, como muestra la salida, hasta que termina de instalarse. La salida del comando systemctl muestra en la salida que el servicio está activo y corriendo.Se crea regla de apertura del puerto 80 de Apache con ufw y con ss -ltn se muestran los puertos escuchando, en este caso el 80 está escuchando.
	 
----------

#### 3.- Instalación y configuración de TOMCAT.	
1. **¿Qué hace el comando?**,**¿Cómo se usa?**
	<p><u>apt  install  –y  tomcat9  tomcat9-admin</u>:instalamos Tomcat y el admin de Tomcat(interfaz).<br>
	<u>systemctl status tomcat9</u>:visualizar el estado de Tomcat<br>
	<u>ss -ltn</u>:puertos que están escuchando(8080)<br>
	<u>sudo apt-get install tomcat9-docs</u>:instalamos documentos de Tomcat<br>
	<u>sudo apt-get install tomcat9-examples</u>:instalamos ejemplos de Tomcat<br>
	<u>nano /etc/tomcat9/tomcat-users.xml</u>:Apertura archivo de configuración usuarios xml<br>
	<u>service tomcat9 start/stop</u>:parar/iniciar Tomcat. 
1. **¿Por qué responde a la pregunta?**,**¿Cómo se interpreta la salida?**
	<p>El instalador nos va mostrando en la salida el progreso de instalación de Tomcat.El comando sustemctl nos indica que el servicio está corriendo y con ss -ltn nos indica que el puerto de Tomcat 8080 está escuchando y configurado correctamente.A continuación modificamos los permisos de usuario para acceder a la interfaz/admin de Tomcat.Con el comando start/stop reiniciamos el servidor para que los cambios tengan efecto.
 	
----------
 
#### 4.- Instalación y configuración de SSH.
1. **¿Qué hace el comando?**,**¿Cómo se usa?**
	<p><u>apt-get install openssh-server</u>:instala SSH.<br>
	<u>systemctl status ssh</u>:estado del servicio SSH. 
	<u>ss -ltn</u>: comprobamos los puertos que están escuchando(22).	
1. **¿Por qué responde a la pregunta?**,**¿Cómo se interpreta la salida?**
	<p>Al lanzar la instalación en la salida se nos indica que SSH ya está instalado y actualizado. Para ver su estado ejecutamos el comando systemctl y la salida nos dice que está activo. Por otro lado para comprobar que está bien instalado y funcionando, ejecutamos el comando ss -ltn y comprobamos en la salida que el puerto 22 está escuchando.

----------

#### 5.- Instalación y configuración de MARIADB.
1. **¿Qué hace el comando?**,**¿Cómo se usa?**
	<p><u>sudo apt-get install mariadb-server </u>:Instala MariaDB<br>
	<u>sudo systemctl status mariadb</u>:comprueba el estado del servicio de MariaDB.
	<u>mysql_secure_installation</u>: Configurar contraseña en MariaDB<br>
	<u>ss -ltn</u>: ver que puertos están escuchando.	
1. **¿Por qué responde a la pregunta?**,**¿Cómo se interpreta la salida?**
	<p>El comando instalador instalará MariaDB tal y como muestra el progreso en la salida.Con el comando systemctl comprobamos en la salida que el servicio está activo y con ss -ltn comprobamos que el puerto correspondiente(3306) está escuchando y está todo correcto.Con el comando musql_secure_installation configuramos varios parámetros de MariaDB, en este caso quitaremos la contraseña y el resto lo dejaremos tal cual, la salida confirma que está todo ok y te agredece el uso del server.

----------

#### 6.- Otros Comandos utilizados.	
1. **sudo su**
	<p> Para trabajar en consolo como super usuario. Se pide contraseña.
1. **clear**
	<p> Limpia la consola o terminal.
1. **cd /sdaf/dsgfs/fdgdfg**
	<p> Para ir a la carpeta que queramos.	
1. **sudo apt update**
	<p>Actualizaciones disponibles.
1. **sudo apt upgrade**
	<p>Instalación de actualizaciones disponibles.
1. **touch hola.html**
	<p> Para crear un archivo en el directorio que nos encontremos.	
1. **chmod 777 hola.html*
	<p> Para dar permisos de lecturaacceso y escritura a un archivo.	
1. **cd /sdaf/dsgfs/fdgdfg**
	<p> Para ir a la carpeta que queramos.	
1. **ufw status/ufw allow 80/tcp**
	<p> Con el primer comando vemos el estado del firewall y las reglas que tiene.	
	<p> Con el segundo generamos una regla de acceso en el firewall, al puerto y protocolo indicado.