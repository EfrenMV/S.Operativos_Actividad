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

Un archivo se almacena físicamente en un dispositivo de almacenamiento, como un disco duro o una unidad SSD. Cuando guardas un archivo en tu computadora,
 el sistema operativo lo divide en bloques de datos y los escribe en ubicaciones específicas del dispositivo. Cada bloque tiene una dirección única, y el sistema mantiene una 
 abla de asignación que indica dónde se encuentra cada parte del archivo. Cuando abres el archivo, el sistema operativo localiza estos bloques y los reagrupa para presentarlos 
 como un archivo completo.

# Ejercicio 4: Mecanismo de acceso a los archivos
## Tareas
### Define los diferentes mecanismos de acceso

1. **Acceso Secuencial:** Los datos se leen o escriben de manera continua, uno después del otro, sin saltarse ninguna parte. Este mecanismo es común en cintas magnéticas o archivos de texto, donde los datos se procesan en el mismo orden en que se almacenan.

2. **Acceso Directo (Aleatorio):** Permite leer o escribir en cualquier parte del archivo directamente, sin necesidad de recorrer los datos en secuencia. Es utilizado en discos duros y SSDs, donde se puede acceder rápidamente a cualquier bloque de información.

3. **Acceso por Índice:** Se utiliza una estructura de índice para localizar rápidamente los datos. El índice almacena las direcciones de los bloques de datos, lo que permite un acceso más rápido que el secuencial. Es común en bases de datos y sistemas de archivos como NTFS.

4. **Acceso por Clúster:** En lugar de acceder a bloques individuales, los datos se organizan en grupos (clústeres) de bloques, lo que mejora la eficiencia de almacenamiento y recuperación. Es utilizado en sistemas de archivos como FAT.

### Escribe un pseudocódigo que muestre cómo acceder a:

1. Un archivo secuencialmente

```C
Abrir archivo en modo lectura
Mientras no sea fin de archivo:
    Leer siguiente registro
    Procesar registro
Cerrar archivo

```
2. Un archivo directamente mediante su posición

```C
Abrir archivo en modo lectura y escritura
Posición = 2   
Ir a posición (Posición)
Leer datos en la posición
Procesar datos
Cerrar archivo

```
3. Un archivo utilizando un índice

```C
Abrir archivo de datos en modo lectura
Abrir archivo de índice en modo lectura
Índice = Buscar en índice la clave deseada
Posición = Obtener posición del índice para la clave
Ir a posición (Posición) en archivo de datos
Leer datos en la posición
Procesar datos
Cerrar archivo de datos
Cerrar archivo de índice

```
### Comparar las ventajas de cada mecanismo dependiendo del caso de uso.

| Mecanismo de Acceso        | Caso de Uso                                        | Ventajas                                                 |
|----------------------------|----------------------------------------------------|----------------------------------------------------------|
| **Acceso Secuencial**       | Archivos de registro, archivos de log, o bases de datos con consultas en orden secuencial. | - Fácil de implementar.                                  |
|                            |                                                    | - Eficiente para procesar grandes volúmenes de datos de forma lineal. |
|                            |                                                    | - Bajo consumo de recursos.                             |
| **Acceso Directo (Aleatorio)** | Archivos grandes, bases de datos, sistemas de gestión de archivos, o cuando se requiere acceso rápido a datos específicos. | - Acceso rápido a cualquier parte del archivo.          |
|                            |                                                    | - Ideal para operaciones de lectura/escritura rápidas.   |
|                            |                                                    | - Menor tiempo de espera, no es necesario leer toda la información. |
| **Acceso por Índice**       | Bases de datos, sistemas de gestión de archivos con búsquedas frecuentes o consultas por claves específicas. | - Búsqueda rápida mediante índices.                     |
|                            |                                                    | - Eficiente para búsquedas y modificaciones rápidas.     |
|                            |                                                    | - Ideal para acceder a datos sin necesidad de leer secuencialmente. |


# Ejercicio 5: Modelo jerárquico y mecanismos de recuperación en caso de falla
### Diseña  un modelo jerárquico para un sistema de archivos con al menos tres niveles de directorios
### Simula una falla en un directorio específico y describe los pasos necesarios para recuperarlo.

### Explica qué herramientas o técnicas de respaldo (backup) utilizarías para evitar pérdida de datos

1. Copia de seguridad completa: Se realiza una copia de todos los archivos importantes. Es simple pero consume más espacio y tiempo.

2. Copia de seguridad incremental: Solo se respaldan los archivos que han cambiado desde el último respaldo, lo que ahorra espacio y tiempo.

3. Copia de seguridad diferencial: Respalda los archivos que han cambiado desde el último respaldo completo, proporcionando un equilibrio entre la rapidez y la capacidad de recuperación.

4. Almacenamiento en la nube: Servicios como Google Drive, Dropbox o Amazon S3 permiten guardar datos de manera remota y accesible desde cualquier lugar.

5. Dispositivos externos: Discos duros o unidades SSD externas para copias locales.

6. RAID (Redundant Array of Independent Disks): Técnica que combina varios discos para mejorar la fiabilidad y la redundancia de los datos, protegiendo contra fallos de discos individuales.

7. Automatización de respaldos: Uso de software que automatiza el proceso de copia de seguridad en intervalos regulares para evitar olvidos o errores humanos.