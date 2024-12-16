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
### Describe las ventajas y desventajas de cada sistema basado en sus componentes

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