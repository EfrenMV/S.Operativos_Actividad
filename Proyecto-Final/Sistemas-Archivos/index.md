<!--Portada-->
<div align="center">

# Sistemas Operativos

### Proyecto Final<br>Sistemas de Archivos

### ISC

### Docente: Jesus Eduardo Alacaraz Chavez

### Alumno: Efren Mendez Villanueva

</div>

___
 
# Índice
- [Ejercicio 1](#ejercicio-1-concepto-y-noción-de-archivo-real-y-virtual)
  - [Define el concepto de archivo real y archivo virtual:](#define-el-concepto-de-archivo-real-y-archivo-virtual)
  - [Proporciona ejemplo de como los sistemas operativos manejan archivos reales y virtuales:](#proporciona-ejemplo-de-cómo-los-sistemas-operativos-manejan-archivos-reales-y-virtuales)
  - [Explica un caso practico donde un archivo virtual sea mas útil que un archivo real:](#explica-un-caso-practico-donde-un-archivo-virtual-sea-mas-útil-que-un-archivo-real)
- [Ejercicio 2](#ejercicio-2-componentes-de-un-sistema-de-archivos)
  - [Identifica los componentes clave de un sistema de archivos ( por ejemplo, metadatos, tablas de asignación, etc.)](#identifica-los-componentes-clave-de-un-sistema-de-archivos--por-ejemplo-metadatos-tablas-de-asignación-etc)
  - [Crea un cuadro comparativo de como estos componentes funcionan en sistemas como EXT4 y NTFS.](#crea-un-cuadro-comparativo-de-como-estos-componentes-funcionan-en-sistemas-como-ext4-y-ntfs)
  - [Describe las ventajas y desventajas de cada sistema basado en sus componentes](#describe-las-ventajas-y-desventajas-de-cada-sistema-basado-en-sus-componentes)
- [Ejercicio 3](#ejercicio-3-organización-lógica-y-física-de-archivos)
  - [Diseña un árbol jerárquico que represente la organización lógica de directorios y subdirectorios](#diseña-un-árbol-jerárquico-que-represente-la-organización-lógica-de-directorios-y-subdirectorios)
  - [Explica cómo se traduce la dirección lógica a la dirección fisica en el disco](#explica-cómo-se-traduce-la-dirección-lógica-a-la-dirección-fisica-en-el-disco)
  - [Proporciona un ejemplo práctico de cómo un archivo se almacena fisicamente](#proporciona-un-ejemplo-práctico-de-cómo-un-archivo-se-almacena-fisicamente)
- [Ejercicio 4](#ejercicio-4-mecanismo-de-acceso-a-los-archivos)
  - [Define los diferentes mecanismos de acceso](#define-los-diferentes-mecanismos-de-acceso)
  - [Escribe un pseudocódigo que muestre cómo acceder a:](#Escribe-un-pseudocódigo-que-muestre-cómo-acceder-a)
  - [Compara las ventajas de cada mecanismo dependiendo del caso de uso.](#compara-las-ventajas-de-cada-mecanismo-dependiendo-del-caso-de-uso)
- [Ejercicio 5](#ejercicio-5-modelo-jerárquico-y-mecanismos-de-recuperación-en-caso-de-falla)
  - [Diseña  un modelo jerárquico para un sistema de archivos con al menos tres niveles de directorios](#diseña--un-modelo-jerárquico-para-un-sistema-de-archivos-con-al-menos-tres-niveles-de-directorios)
  - [Simula una falla en un directorio específico y describe los pasos necesarios para recuperarlo.](#simula-una-falla-en-un-directorio-específico-y-describe-los-pasos-necesarios-para-recuperarlo)
  - [Explica qué herramientas o técnicas de respaldo (backup) utilizarías para evitar pérdida de datos](#explica-qué-herramientas-o-técnicas-de-respaldo-backup-utilizarías-para-evitar-pérdida-de-datos)

# Ejercicio 1: Concepto y noción de archivo real y virtual
## Tareas
### Define el concepto de archivo real y archivo virtual

#### Archivo Real:
Aquel archvio fisico el cual existe en un soporte tangible, como papel, discos curos, cintas magnéticas etc..

#### Archivo Virtual:
Archivos los cuales simplemente existen en el entorno digital/virtual como su nombre lo indica, por ejemplo redes o en la nube

### Proporciona ejemplo de cómo los sistemas operativos manejan archivos reales y virtuales

En el caso de los archivos reales tenemos el echo de las copias de seguridad las cuales mayormente estan echas en el disco duro, ssd etc

Mientras que los digitales podrian ser archivos almacenados en la lube por ejemplo teniendo el uso de google drive, dropbox etc. Tambien tenemos los archivos virtuales que no se crean en el disco si no en la ram, estos siendo temporales. 

### Explica un caso practico donde un archivo virtual sea mas útil que un archivo real

En el caso de tener que trabajar de forma lejana, donde las personas que trabajan estan muy lejos del area, en estos momentos manejar archivos virtuales donde se manejen las cosas en la nube es una mejor opción


# Ejercicio 2: Componentes de un sistema de archivos
## Tareas

### Identifica los componentes clave de un sistema de archivos ( por ejemplo, metadatos, tablas de asignación, etc.)

1. Metadatos: La información de los archivos pero sin tener el archivo perse
    * Nombre del archivo
    * Tamaño del archivo
    * Tipo de archivo
    * Fecha de creación
    * Fecha de ultima modificación
    * Fecha de último acceso
    * Permiso de acceso
    * Propietario del archivo
    * Estado de los bloques de datos

2. Tablas de asignación (o estructuras de asignación de espacio): Responsables de gestionar el espacio de almacenamiento físico en el dispositivo
    * Tabla de asignación de archivos (FAT)
    * Inodo (Inode)
    * Manejo de bloques

3. Directorios: Estructuras que organizan los archivos en un sistema de archivos
    * Nombre del archivo
    * Enlaces al inodo o tabla de asignación

4. Indice de archivo(o indice de ubicación): Usados para ubicar     rapidamente los archivos, estos son indices que pueden ser tanto como una tabla o una lista que almacena información sobre la ubicacion de los archivos
    * NTFS

5. Bloques de datos: Siendo las unidades mas pequeñas de almacenamiento en el disco estos contienen la información real del archivo 

6. Journaling (registro de transacciones): Utilizado en sistemas de archivos como ext3/ext4 o NTFS, este garantiza la integridad de los datos

### Crea un cuadro comparativo de como estos componentes funcionan en sistemas como EXT4 y NTFS.
| **Componente**            | **EXT4 (Linux)**                                               | **NTFS (Windows)**                                             |
|---------------------------|---------------------------------------------------------------|---------------------------------------------------------------|
| **Metadatos**              | Se almacenan en los **inodos**, que contienen información como el tamaño, tipo, fecha de modificación y permisos del archivo. | Los metadatos se almacenan en el **MFT (Master File Table)**, que incluye la información similar a los inodos, como el tamaño del archivo, permisos, fecha de modificación, etc. |
| **Tabla de asignación**    | **Inodos**: Los inodos contienen punteros a los bloques de datos y gestionan la asignación de espacio en el disco. Cada archivo tiene un inodo único. | **MFT**: La MFT es una tabla de asignación que contiene registros para todos los archivos y directorios. Cada entrada en la MFT tiene información sobre el archivo y la ubicación de sus datos en el disco. |
| **Directorios**            | Los directorios son archivos especiales que contienen una lista de nombres de archivos y su respectivo número de inodo. | Los directorios en NTFS son archivos especiales que contienen una lista de nombres de archivos junto con las entradas correspondientes en la MFT. |
| **Índice de archivo**      | No tiene un índice centralizado como tal, pero cada archivo tiene un inodo que contiene la dirección de los bloques de datos. Los directorios actúan como índices para los archivos. | **MFT**: Cada archivo y directorio tiene una entrada en la MFT, que actúa como un índice para acceder a los bloques de datos del archivo. |
| **Bloques de datos**       | Los archivos están divididos en bloques de datos, que son unidades de almacenamiento físico. EXT4 permite la asignación de bloques de tamaño variable (generalmente entre 1 KB y 4 KB). | Los archivos también se dividen en bloques o clusters. NTFS usa clusters de tamaño variable, generalmente entre 512 bytes y 64 KB. |
| **Journaling (Registro de transacciones)** | **Sí**: EXT4 utiliza journaling para mantener la integridad del sistema de archivos, registrando los cambios antes de que se apliquen. | **Sí**: NTFS también utiliza journaling para mantener la coherencia del sistema de archivos, asegurando la recuperación de datos en caso de un fallo. |
| **Superbloque**            | El superbloque de EXT4 contiene información clave sobre el sistema de archivos, como el número total de bloques, el número de bloques libres y el tamaño de los bloques. | NTFS no utiliza un superbloque como tal, pero la **MFT** y el **boot sector** sirven como elementos centrales para el inicio y la gestión del sistema de archivos. |
| **Enlaces duros y simbólicos** | **Enlaces duros**: EXT4 soporta enlaces duros, que permiten que varios nombres de archivo apunten al mismo inodo. <br> **Enlaces simbólicos**: También soporta enlaces simbólicos (soft links). | **Enlaces duros**: NTFS soporta enlaces duros, aunque su uso está limitado a archivos dentro del mismo volumen. <br> **Enlaces simbólicos**: También soporta enlaces simbólicos, funcionando de manera similar a EXT4. |
| **Seguridad (Permisos de acceso)** | Usa el sistema de permisos típico de Linux, basado en **propietarios** (usuario y grupo) y **permisos** (lectura, escritura, ejecución). | NTFS soporta permisos más complejos basados en **ACLs** (Access Control Lists), que permiten asignar permisos más detallados para usuarios y grupos. |
| **Recuperación de datos**  | **Journaling** asegura que en caso de un fallo, los cambios pendientes sean recuperados al reiniciar el sistema. | **Journaling** en NTFS garantiza la recuperación de datos tras un apagón o fallo inesperado del sistema. Además, NTFS incluye soporte para la **recuperación de archivos** mediante herramientas de reparación del sistema. |


### Describe las ventajas y desventajas de cada sistema basado en sus componentes
| **Aspecto**              | **EXT4 (Linux)**                                               | **NTFS (Windows)**                                             |
|--------------------------|---------------------------------------------------------------|---------------------------------------------------------------|
| **Ventajas**              | - **Journaling** para evitar la corrupción de datos. <br> - Menos susceptible a la fragmentación. <br> - Eficiente con grandes volúmenes de datos y menos fragmentación. <br> - Menor sobrecarga en comparación con NTFS. <br> - Soporta enlaces simbólicos y duros. <br> - Compatible con herramientas de recuperación en Linux. <br> - Soporta volúmenes de hasta 1 exabyte y archivos de hasta 16 terabytes. | - **Journaling** asegura recuperación de datos tras fallos. <br> - Soporta **ACLs (Access Control Lists)** para un control detallado de permisos. <br> - Soporta **encriptación de archivos (EFS)**. <br> - **Compresión** de archivos y directorios. <br> - Soporta volúmenes de hasta 16 exabytes y archivos de hasta 16 terabytes. <br> - Compatible con la mayoría de herramientas en Windows. <br> - Buen soporte para recuperación avanzada de archivos y sistema. |
| **Desventajas**           | - No es compatible de manera nativa con Windows. <br> - No tiene soporte para **ACLs** avanzadas. <br> - La recuperación avanzada puede ser más difícil comparado con NTFS. <br> - La gestión de permisos es más simple que NTFS. | - Puede sufrir fragmentación, aunque tiene algunas optimizaciones. <br> - Mayor sobrecarga de rendimiento debido a su complejidad (por ejemplo, ACLs y compresión). <br> - Compatible con Linux a través de **ntfs-3g**, pero la integración no es tan robusta. |


# Ejercicio 3: Organización lógica y física de archivos 
## Tareas
### Diseña un árbol jerárquico que represente la organización lógica de directorios y subdirectorios

### Explica cómo se traduce la dirección lógica a la dirección fisica en el disco

1. El sistema operativo recibe una solicitud de acceso a un archivo, usando una dirección lógica.
2. El sistema de archivos consulta su tabla de asignación para traducir esta dirección lógica a una dirección física.
3. El sistema operativo usa esta dirección física para localizar los datos en el disco.
4. El controlador de disco accede a los sectores físicos del disco para leer o escribir los datos.

### Proporciona un ejemplo práctico de cómo un archivo se almacena fisicamente

1. Creación del archivo
Supongamos que un usuario crea un archivo de texto llamado documento.txt en su computadora. El sistema operativo le asigna una dirección lógica para este archivo. El archivo contiene el siguiente texto:

Copiar código
Hola, este es un archivo de ejemplo.
Este archivo es inicialmente solo un conjunto de datos que se gestionan lógicamente por el sistema operativo.

2. Estructura del sistema de archivos
El sistema de archivos (por ejemplo, NTFS, FAT32 o ext4) organiza el almacenamiento en bloques. Un bloque es la unidad mínima de almacenamiento de datos en un disco. En el caso de un archivo de texto, el sistema de archivos dividirá el contenido en varios bloques si el archivo es grande, o puede caber en uno solo si es pequeño.

Tamaño de bloque: Los bloques pueden tener tamaños típicos de 4 KB, 8 KB o 16 KB, dependiendo del sistema de archivos y la configuración del disco.
3. Asignación de bloques lógicos
El sistema de archivos asigna bloques lógicos a documento.txt. Supongamos que el archivo tiene 500 bytes de tamaño. Esto podría ocupar un solo bloque de 4 KB en el disco, porque cada bloque tiene un tamaño mayor que el archivo en sí. En este caso, la dirección lógica del archivo puede corresponder al bloque 10 del sistema de archivos, lo que significa que el archivo está contenido en el bloque 10 de la tabla de asignación.

4. Conversión de dirección lógica a dirección física
Una vez que el sistema de archivos ha asignado un bloque lógico para el archivo, el siguiente paso es convertir esa dirección lógica en una dirección física. El sistema de archivos necesita saber en qué parte del disco duro se encuentra ese bloque lógico (por ejemplo, bloque 10) y traducirlo a su ubicación física real.

Un disco duro tiene una estructura jerárquica con pistas y sectores. Supongamos que el bloque lógico 10 corresponde al sector 512 de la pista 3 en el cilindro 5 del disco. Esta es la dirección física donde los datos del archivo se almacenarán.
5. Almacenamiento físico en el disco
El sistema operativo, al hacer la conversión de la dirección lógica a la física, envía la solicitud al controlador de disco para escribir los datos del archivo en el sector 512 de la pista 3, cilindro 5 del disco.

Sector 512 de la pista 3, cilindro 5: Esta es la ubicación física específica en el disco donde los datos de documento.txt se almacenarán. El controlador de disco accede a la ubicación exacta de la superficie del disco y escribe los datos allí.
En este caso, el archivo documento.txt podría ocupar un solo bloque (o varias partes si fuera más grande) y se almacenaría en el disco de manera física en ese sector específico.
6. Lectura del archivo
Cuando un usuario o una aplicación quiere acceder al archivo documento.txt, el proceso es el siguiente:

Solicitud del archivo: El sistema operativo recibe una solicitud para leer documento.txt.
Dirección lógica: El sistema de archivos consulta la tabla de asignación y encuentra que el archivo está almacenado en el bloque lógico 10.
Conversión a dirección física: El sistema de archivos traduce el bloque lógico 10 a la dirección física real: sector 512 de la pista 3, cilindro 5.
Acceso físico al disco: El controlador de disco accede a esa ubicación física, lee los datos y los devuelve al sistema operativo.
Devolución de los datos: El sistema operativo devuelve los datos del archivo a la aplicación solicitante (en este caso, el texto que contiene el archivo).
7. Resumen visual de la ubicación:
Dirección lógica: Bloque 10
Dirección física: Sector 512, Pista 3, Cilindro 5 (en el disco)
8. Fragmentación de archivos
Si el archivo fuera más grande y no pudiera almacenarse en un solo bloque, el sistema de archivos podría fragmentarlo y almacenar partes del archivo en bloques no contiguos. En este caso, la tabla de asignación de archivos gestionaría estos bloques dispersos, y el sistema operativo realizaría múltiples traducciones de direcciones lógicas a físicas para acceder a todos los fragmentos del archivo.
# Ejercicio 4: Mecanismo de acceso a los archivos
## Tareas
### Define los diferentes mecanismos de acceso
### Escribe un pseudocódigo que muestre cómo acceder a:
1. Un archivo secuencialmente
2. Un archivo directamente mediante su posición
3. Un archivo utilizando un índice
### Compara las ventajas de cada mecanismo dependiendo del caso de uso.

# Ejercicio 5: Modelo jerárquico y mecanismos de recuperación en caso de falla
### Diseña  un modelo jerárquico para un sistema de archivos con al menos tres niveles de directorios
### Simula una falla en un directorio específico y describe los pasos necesarios para recuperarlo.
### Explica qué herramientas o técnicas de respaldo (backup) utilizarías para evitar pérdida de datos