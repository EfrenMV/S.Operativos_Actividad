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
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
- [Ejercicio 3](#ejercicio-3-organización-lógica-y-física-de-archivos)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
- [Ejercicio 4](#ejercicio-4-mecanismo-de-acceso-a-los-archivos)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
- [Ejercicio 5](#ejercicio-5-modelo-jerárquico-y-mecanismos-de-recuperación-en-caso-de-falla)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)
  - [Sub-sección 2.1](#sub-sección-21)

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
### Disela un árbol jerárquico que represente la organización lógica de directorios y subdirectorios
### Explica cómo se traduce la dirección lógica a la dirección fisica en el disco
### Proporciona un ejemplo práctico de cómo un archivo se almacena fisicamente

# Ejercicio 4: Mecanismo de acceso a los archivos
## Tareas
### Define los diferentes mecanismos de acceso
### escribe un pseudocódigo que muestre cómo acceder a:
1. Un archivo secuencialmente
2. Un archivo directamente mediante su posición
3. Un archivo utilizando un índice
### Compara las ventajas de cada mecanismo dependiendo del caso de uso.

# Ejercicio 5: Modelo jerárquico y mecanismos de recuperación en caso de falla
### Diseña  un modelo jerárquico para un sistema de archivos con al menos tres niveles de directorios
### Simula una falla en un directorio específico y describe los pasos necesarios para recuperarlo.
### Explica qué herramientas o técnicas de respaldo (backup) utilizarías para evitar pérdida de datos