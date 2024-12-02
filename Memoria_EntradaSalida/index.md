<!--Portada-->
<div align="center">

# Sistemas Operativos

### Actividad<br>Administración de memoria

### ISC

### Docente: Jesus Eduardo Alacaraz Chavez

### Alumno: Efren Mendez Villanueva

</div>

___
<!--3.1 Política y filosofía-->
<div align="center">

# **3.Administraciòn de Memoria** 
</div>

# 3.1 Politica y Filsoifa

## Fragmentación Interna vs Externa

### Fragmentación interna:  
Como su palabra lo indica **interna** nos da a entender que la particiones ocurren en la memoria, ahora estas particiones estan divididas en bloques con tamaños especificos 

por ejemplo:

podemos observar una Fragmentación interna la cual esta divida en partes iguales donde cada parte sera encargada de manejar los procesos

![Bloques de memoria ejemplos](Imagenes/memoriaInterna2.png "Bloques de memoria")

Al memento de asignarle estos procesos estos eran acomodados en los bloques que tenemos
![](Imagenes/memoriaInterna.png)

Como se puede observar estos al ser colocados generan un desperdicio puesto que no estan aprovechando el 100% de cada uno.

***conclución:***<br>
La fragmentación interna puede llegar a generar desperdicios de memoria si un proceso no usa lo suficiente asignado puesto que este sobrando no se vuelve usar simplemente queda en nada

### Framgentación externa ### 
La gragmentación externa como su contraparte tambien puede llegar desperdicios pero por otra razones, puesto que esta es guardada de forma dispersa entonces tenemos desperdicios en espaciso que no estamos usando

por ejemplos:

aqui podemos obersvar una imagen de un disco HDD

![Disco HDD](Imagenes/externa.png "Disco HDD")

Al llegarse queda algo asi

![Disco HDD FULL](Imagenes/externo2.png)

Podemos observar que los procesos estan gurdados de forma aleatoria lo cual genera espacios entre ellos

visto de otra forma lo tenemos asi

![Disco HDD POV2](Imagenes/externa0.1.png)

Esto tiene una solición donde se le puede aplicar una desfragmentación lo cual lo dejara asi

![Disco HDD POV2 desfragmentado](Imagenes/externa0.2.png)

Esto ayuda a optimizar las busquedas muchisimo, aunque los SSD no necesariamente ocupan esto pero los HDD si

## Resuen completo
|  Fragmentación Intera  | Fragmentación Externa  
|  ------- |:----:
|  Ocurre dentro de un bloque asignado| Ocurre fuera de bloques asignados
|  Desperdicio dentro de la memoria asignada| Desperdicio por espacios dispersos 
| Relacionada con Ram y memoria virtual| Ocurre en RAM,memoria virutal, HDD o SDD
| No se puede desfragmentar | Se puede desfragmentar|

## Politicas de remplazo 

**Fifo(First In, First Out):** 
En este algoritmo se atiende al que llego primero, estos deben esperar una lista/cola donde se estaran esperando cada proceso,<breste>
proceso en ejecución no puede ser parado hasta que termite

ejemplo:
|Proceso|  Rafaga de CPU  | Tiempo de llegada  | 
|:--------: |   --------       |  :----:            | 
| A     |  8              |     0              | 
| B     |  6              |     2              |  
| C |  4              |     4              |    
| D |  2              |     6              |   

Como se observa en el ejemplo de arriba tenemos diferentes proceos con diferentes tiempos de llegada, estos seran ejecutados de la siguiente forma
1. Se inicia el proceso A que tiene un tiempo de llegada de 0s y le tomara 8s en acabar
2. Cuadno el proceso A le falten 6s llega el proceso B pero este entrara en espera de que el proceso A termine
3. Cuadno el proceso A le falten 2s llega el proceso c pero este entrara en espera de que el proceso B termine
3. Cuando el proceso B le falten 2s llega el proceso d pero este entrara en espera de que el proceos C termine
4. Inician los procesos faltantes y terminan en este orden 
      * B
      * C
      * D

**LRU (Least Recently Used):**

**Optimal(OPT)**

**Clock**

**NFU(Not frequently Used)**

**Random**

**Segunda Chance**

# 3.2 Memoria real

## Programa en C de particiones fijas
```C
#include <stdio.h>
#include <stdlib.h> //Para manejar la memoria

#define cantidadParticiones 5 //Numero de particiones maximas

//Estructura
typedef struct{
    int tamaño;    //Para el tamaño de nuestros procesos
    int ocupado;   // 0 no estara ocupado 1 estara ocupado
    int id;        // Para el id del proceso
}Particion;

// inicializar las particiones
void inicializar(Particion particiones[]) {
    for (int i = 0; i < cantidadParticiones; i++) {
        printf("Ingrese el tamaño de la partición %d: ", i + 1);
        scanf("%d", &particiones[i].tamaño);
        particiones[i].ocupado = 0;
        particiones[i].id = -1;
    }
}

// Asignar procesos
void asignar(Particion particiones[]) {
    int id, tamaño;
    printf("\nIngrese el ID del proceso: ");
    scanf("%d", &id);
    printf("Ingrese el tamaño del proceso: ");
    scanf("%d", &tamaño);

    int asignado = 0;
    for (int i = 0; i < cantidadParticiones; i++) {
        if (particiones[i].ocupado == 0 && particiones[i].tamaño >= tamaño) {
            particiones[i].ocupado = 1;
            particiones[i].id = id;
            printf("Proceso %d asignado a la partición %d\n",  id, i + 1);
            asignado = 1;
            break;
        }
    }

    if (!asignado) {
        printf("No se pudo asignar el proceso %d debido a falta de espacio.\n", id);
    }
}

// Función para liberar una partición
void liberar(Particion particiones[]) {
    int id;
    printf("\nIngrese el ID del proceso a liberar: ");
    scanf("%d", &id);

    int liberado = 0;
    for (int i = 0; i < cantidadParticiones; i++) {
        if (particiones[i].ocupado == 1 && particiones[i].id == id) {
            particiones[i].ocupado = 0;
            particiones[i].id = -1;
            printf("Partición %d liberada.\n", i + 1);
            liberado = 1;
            break;
        }
    }

    if (!liberado) {
        printf("No se encontró el proceso %d para liberar.\n", id);
    }
}

// Mostrar el estado actual de las particiones
void mostrar(Particion particiones[]) {
    printf("\nEstado actual de las particiones:\n");
    for (int i = 0; i < cantidadParticiones; i++) {
        printf("Partición %d: Tamaño %d, ", i + 1, particiones[i].tamaño);
        if (particiones[i].ocupado == 1) {
            printf("Ocupado por el proceso %d\n", particiones[i].id);
        } else {
            printf("Libre\n");
        }
    }
}

int main(){
    Particion particiones[cantidadParticiones];
    int opc;

    // Inicializamos las particiones
    inicializar(particiones);

    do{
        printf("\n---Menu---\n"
        "1.-Asignar proceso a una partición\n"
        "2.-liberar particion\n"
        "3.-Mostrar particiones\n"
        "4.-Salir \n");
        scanf("%d",&opc);

        switch(opc){
            case 1:
                asignar(particiones);
                break;
            case 2:
                liberar(particiones);
                break;
            case 3:
                mostrar(particiones);
                break;
            case 4:
                printf("Saliendo..");
                break;
            default:
                printf("Opcion invalida, degite una opcion valida por favor");
        }
    } while (opc != 4);
    return 0;
}
```

## Algoritmo para calcular procesos utilizando el algoritmo de "primera cabida"

1. Inicio
2. Leer el tamaño de cada partición
3. Leer el tamaño del proceso asignar
4. Comparar tamaños con los bloques y encontrar el cual puede asignarle el proceso
5. Si se encuentra verificar si esta ocupado
6. Si no esta ocupado usarlo y marcarlo como ocupad
6. Si esta ocupado buscar otro
7. Si se encuentra otro utilizar ese y marcarlo como cupado

    Si no hay otro que pueda cubrir el espacio imprimir "no se cuenta con suficiente espacio"
8. Fin

# 3.3 Organización de memoria virtual

### Paginación y segmentación

**Segmentación** Es la divición de la memoria primeria de un ordenador, esto ayuda para proteger modulos de segmentos contra accesos no autorizados 

**Paginación de memoria** Esta es la divición en pequeñas partes o páginas a un programa 

aqui mismo contamos con los **marcos** estos se les denomina como numero de pagina fisica esta pagina fisica es asignada a un proceso de forma exclusiva

### Programa que simule una tabla de páginas para procesos con acceso aleatorio a memoria virtual

```C
#include <stdio.h>
#include <stdlib.h>

Realmente no se que pedo :)

```
# 3.4 Administración de memoria virtual

### Codigo con el algoritmo "Least Recently Used" (LRU)

### Diagrama para el proceso de traducción de direciones virtuales a fisicas en un sistema con memoria virtual

## Integración

### Analizar un sistema operativo moderno (por ejemplo Linux o Windows) e indentificar como administra la memoria virtual

### Simulacion del swapping de procesos en memoria virtual

<div align="center">

# **4.Administración de Entrada/Salida**
</div>

# 4.1 Dispositivos y menejadores de dispositivos

### Diferencia entre dispositivos de bloque y dispositivos de caracter

### Programa manejador de dispositivos para un dispositivo virtual de entrada

# 4.2 Mecanismos y funciones de los manejadores de dispositivos 

### Interrupciones por E/S y su administración con el S.O

### Programa de interrupciones 

# 4.3 Estructuras de datos para manejo de dispositivos

### Que es una cola de E/S y una simulación de una cola con prioridad

### Programa para manejar las operaciones de dispositivos utilizando una tabla de estructuras

# 4.4 Operaciones de Entrada y Salda

### Diseña un flujo que describa el proceso de lectura de un archivo desde un disco magnético. Acampañado con un programa basico para simular el proceso

### Programa que realice operaciones de entrada/salida asincronas usando archivos