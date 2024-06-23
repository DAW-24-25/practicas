# Prácticas Desarrollo de Aplicaciones Web

(<a href="../Readme.md">volver al índice</a>)

# Práctica 0. Instalación y configuración del Software

En esta práctica indicaremos como instalar y configurar el software utilizado en la asignatura, tal como se ha instalado en los ordenadores del laboratorio, por si necesitáis instalarlo en vuestros ordenadores.


Descargue y descomprima, en una carpeta, el siguiente software.
Supongamos que trabajamos en Windows y que la carpeta utilizada para descomprimir los ficheros será C:\DAW

## Java JDK 21

https://download.oracle.com/java/21/latest/jdk-21_windows-x64_bin.zip

```
C:\DAW\jdk-21.0.3
```

## Apache Netbeans 22

https://www.apache.org/dyn/closer.lua/netbeans/netbeans/22/netbeans-22-bin.zip

```
C:\DAW\netbeans
```

Configure Apache Netbeans para que inicie y utilice la versión de java anterior y no de conflicto con otras versiones de netbeans instaladas, editando el fichero "C:\DAW\netbeans\etc\netbeans.conf", modificando el contenido con:

```
...

netbeans_default_userdir="${DEFAULT_USERDIR_ROOT}/DAW"
netbeans_default_cachedir="${DEFAULT_CACHEDIR_ROOT}/DAW"

...
#netbeans_jdkhome="/path/to/jdk"
netbeans_jdkhome="C:\DAW\jdk-21.0.3"

...
```

Cree, en C:\DAW un acceso directo, llamado "Apache Netbeans 22", apuntando a C:\DAW\netbeans\bin\netbeans64.exe; para ello basta con que arrastre este fichero y pulse Ctrl + Shift antes de soltarlo (luego cambie el nombre).

Inicie Apache Netbeans y compruebe que utiliza la configuración anterior, mediante la opción del menu Help - About.
 
## Instalar GlassFish 7.0.14 y Apache Derby (Java DB)

Desde Apache Netbeans, acceda a la opción del menú Window y elija Services. Esto nos abrirá una pestaña donde podemos instalar y configurar, entre otros aspectos, el servidor de aplicaciones y el Sistema Gestor de Bases de Datos.

En la pestaña Services, haga clic derecho en la opción Servers y elija "Add Server..."

En el asistente, elija GlassFish Server, escriba como nombre "GlassFish Server 7.0.14" y pulse Next. En la siguiente pantalla, establezca la carpeta de ubicación C:\DAW\GlassFish-7.0.14, elija la versión de glassfish a instalar desde el desplegable, acepte los términos de licencia y pulse el botón Download. Tras la descarga, pulse Next y en la siguiente pantalla deja el resto de las opciones por defecto y pulsa Finish.

La instalación de GlassFish (7.0.14) incluye la instalación de Java DB (ahora Apache Derby), en concreto la versión 10.15.2.0. Apache Derby o Java DB un SGBD ideal para entornos de desarrollo, aunque no sería adecuado para entornos de producción. Para entornos de producción serían nás adecuados SGBDs como MySQL, PostgreSQL, etc.

Puede comprobar y establecer la configuración del SGBD en la pestaña Services, desplegando la opción "Databases". Haga clic derecho en Java DB, elija "Properties.." y en "Database Location" establezca la ruta donde se almacenarán las bases de datos, en nuestro caso, C:\DAW\BD.

Ahora, ya podría crear una nueva base de datos, haciendo clic derecho en Java DB, elijiendo "Create Database.." y completando el asistente con el nombre de la BD, el usuario y la contraseña.


## Recapitulando

Al finalizar la práctica, deberá contar en la carpeta C:\DAW con los siguientes elementos:

```
C:\DAW
    --- jdk-21.0.3/         Directorio con la instalación de Java JDK 21
    --- netbeans/           Directorio con la instalación de Apache Netbeans 22
                            donde habrá modificado el fichero netbeans/etc/netbeans.conf
    --- GlassFisk-7.0.14/   Directorio con la instalación de GlassFish 7.0.14
                --- javadb/ Directorio con la instalación de Java DB de Glassfish
    --- BD/                 Directorio para la ubicación de las bases de datos creadas con Java DB
    --- Apache Netbeans 22  Fichero ejecutable de Netbeans (Acceso directo a netbeans\bin\netbeans64.exe)

```







