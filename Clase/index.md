<div align="center">

# Sistemas Operativos

### Proyecto Final<br>Actividades en clase

### ISC

### Docente: Jesus Eduardo Alacaraz Chavez

### Alumno: Efren Mendez Villanueva

</div>

___
 
# Índice
* [Fibonachi](#figonachi)
- [Potencia_Suma](#potencia_suma)
- [Divición_Resta](#divición_resta)
- [Dispositivos](#dispositivos)
- [Prueba de escritorio Deker](#prueba-de-escritorio-dekker)   
- [Prueba de escritorio Peterson](#prueba-de-escritorio-peterson)

  # Figonachi
  
  ```C
  #include <stdio.h>
   
    int fibonacci(int n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n - 1) + fibonacci(n - 2);
    }

    int main() {
    int n;
    printf("Introduce un número: ");
    scanf("%d", &n);
    
    printf("El número de Fibonacci en la posición %d es: %d\n", n, fibonacci(n));
    return 0;
    }
  ```
  # Potencia_Suma
  
  ```C
   #include <stdio.h>

    int multiplicar(int a, int b) {
    int r = 0;
    for (int i = 0; i < b; i++) {
        r += a;
    }
    return r;
    }

    int potencia_con_suma(int base, int exponente) {
    int r = 1;
    for (int i = 0; i < exponente; i++) {
        r = multiplicar(r, base);
    }
    return r;
    }

    int main() {
    int base, exponente;
    printf("Introduce la base: ");
    scanf("%d", &base);
    printf("Introduce el exponente: ");
    scanf("%d", &exponente);
    int r = potencia_con_suma(base, exponente);
    printf("%d elevado a la %d es: %d\n", base, exponente, r);
    return 0;
    }

  ```
  # Divición_Resta
  
  ```C
  #include <stdio.h>

    int dividir (int dividendo, int divisor) {
    int cociente = 0;

    while (dividendo >= divisor) {
        dividendo -= divisor;
        cociente++;
    }

    return cociente;
    }

    int main() {
    int dividendo, divisor;
    printf("Ingresa el dividendo: ");
    scanf("%d", &dividendo);
    printf("Ingresa el divisor: ");
    scanf("%d", &divisor);

    if (divisor == 0) {
        printf("Error: No pudes divir por 0 tilin.\n");
    } else {
        int cociente = dividir(dividendo, divisor);
        printf("El cociente de la división es: %d\n", cociente);
    }

    return 0;
    }

  ```

  # Librerias para camara,impresora y escaner

  **Buscar que librerias usar para mi camara, impresora, escaner**

    * Java

        *Camaras:*
        1. OpenIMAJ
            * GitHub OpenIMAJ
        2. JavaCV(Wrapped de OpenCV para Java)<br> 
           * JavaCV
        3. JWF(Java Media Framework)


        *Impresoras*
        1. Java Print Service Api

        *Escaneres:*
        1. Twain4j


    * C

        *OpenCV(C/C++)*
        1. OpenCV

        *Impresoras*
        1. WinAPI(Windows)

        *Escáneres*
        1. SANE(Scanner Access Now Easy)
        2. Twain(Twain Toolkit)

* Info extra
<br> *TWAIN*: Usado principalmente en Windwos para escáneres.
<br> *SANE*: Más común en Linux escáneres.
<br> OpenCV*: Funciona en Windows, Linux y macOS para cámaras.

# Dispositivos

## Actividad 1

**1. ¿Qué tipos de dispositivos se muestran en la salida de `lsblk`?**

- **Particiones**: La salida de `lsblk` muestra las particiones conectadas al sistema, identificadas con un nombre similar a `nvme0n1p1`, donde el prefijo indica el tipo de dispositivo (en este caso, un disco NVMe) y el sufijo indica una partición de dicho dispositivo.
- **Discos o SSD**: También se muestra información sobre el disco o SSD principal del sistema, que aparecería sin un número de partición (por ejemplo, `nvme0n1`).
- **Aplicaciones**: Pueden aparecer dispositivos tipo "loop", que son imágenes de disco montadas como si fueran particiones (por ejemplo, para montar contenedores o archivos ISO), y la salida muestra el tamaño y el uso de estos dispositivos.

**2. ¿Cuál es la diferencia entre `lsusb` y `lspci`?**

- **`lsusb`**: Muestra los dispositivos conectados a los puertos USB. Esto incluye dispositivos como teclados, ratones, impresoras, discos duros externos, entre otros.
- **`lspci`**: Muestra los dispositivos conectados al bus PCI, que incluyen componentes internos como tarjetas gráficas, controladores de red, tarjetas de sonido, controladores SATA y otros periféricos internos.

**3. ¿Qué información adicional proporciona `dmesg | grep usb`?**

El comando `dmesg | grep usb` muestra los mensajes del kernel relacionados con dispositivos USB, tales como:
- Dispositivos USB que se han conectado o desconectado.
- Errores o advertencias del kernel respecto a los dispositivos USB.
- Información sobre el estado y configuración de los dispositivos USB.

## Actividad 2

**1. ¿Qué dispositivos de almacenamiento están conectados a su sistema?**

- Usando `fdisk -l` y `blkid`, podrás ver los discos y particiones conectados, tales como discos duros internos (por ejemplo, `/dev/sda`), discos duros externos o particiones asociadas a unidades específicas.

**2. ¿Qué particiones están montadas actualmente?**

- Usando `df -h`, se puede observar qué particiones están montadas y cuánta capacidad de espacio están utilizando.

**3. ¿Qué tipo de sistemas de archivos se usan en las particiones?**

- El comando `blkid` te proporcionará el tipo de sistema de archivos para cada partición, como `ext4`, `ntfs`, `vfat`, entre otros.

## Actividad 3

**1. ¿Qué eventos genera cada dispositivo al interactuar con ellos?**

- **Teclado**: Genera eventos al presionar y soltar las teclas (códigos de escaneo).
- **Mouse**: Genera eventos de movimiento (mover el cursor) y clics (botones presionados).
- **Controladores USB**: Generan eventos relacionados con la conexión o desconexión de dispositivos USB, como la detección de nuevos dispositivos o errores.

**2. ¿Cómo se identifican los dispositivos en `/proc/bus/input/devices`?**

Los dispositivos se identifican por sus atributos, tales como:
- **Name**: El nombre del dispositivo (por ejemplo, "keyboard" para un teclado).
- **Handlers**: Los controladores que manejan los dispositivos.
- **Event**: El evento asignado al dispositivo (por ejemplo, `event0`, `event1`).

## Actividad 4

**1. ¿Qué salidas de video están disponibles en su sistema?**

Usando el comando `xrandr`, puedes ver las pantallas conectadas, sus resoluciones y su estado (por ejemplo, "connected" o "disconnected").

**2. ¿Qué dispositivos de sonido se detectaron?**

El comando `aplay -l` lista las tarjetas de sonido detectadas, como tarjetas integradas, tarjetas externas o dispositivos USB relacionados con el sonido.

**3. ¿Qué procesos están usando la tarjeta de sonido?**

El comando `lsof /dev/snd/*` muestra qué procesos están utilizando la tarjeta de sonido, como aplicaciones de reproducción de audio o servicios del sistema que interactúan con el hardware de sonido.

## Actividad 5

**1. ¿Qué ventajas tiene usar un script para recopilar esta información?**

- **Automatización**: Ejecutar un script permite recopilar toda la información de manera automatizada sin tener que ejecutar los comandos individualmente.
- **Eficiencia**: Facilita la recopilación de información para tareas de diagnóstico o administración del sistema, ya que genera un reporte completo.
- **Facilidad de reutilización**: El script puede ser reutilizado en múltiples máquinas o en diferentes momentos.

**2. ¿Qué cambios realizaría para personalizar el script?**

- Puedes agregar más comandos si necesitas más información (por ejemplo, `top` para ver el uso del CPU o `free -h` para el uso de memoria).
- Puedes agregar detalles como fecha y hora al archivo de salida para llevar un registro de cuándo se recopiló la información.
- Puedes redirigir la salida a un archivo comprimido o agregar filtrado para mostrar solo la información relevante.

## Actividad 6

**1. ¿Qué comando encontró más útil y por qué?**

- El comando más útil puede variar según el contexto. Sin embargo, **`lsblk`** es muy útil porque proporciona una visión clara de todos los discos y particiones en el sistema, lo cual es esencial para la administración de almacenamiento.

**2. ¿Qué tan importante es conocer los dispositivos conectados al sistema?**

Es crucial conocer los dispositivos conectados al sistema porque esto permite:
- Diagnosticar problemas de hardware.
- Gestionar el almacenamiento de manera eficiente.
- Monitorear el uso de recursos como memoria, CPU, y dispositivos de entrada y salida.

**3. ¿Cómo podrían estos conocimientos aplicarse en la administración de sistemas?**

Estos conocimientos son fundamentales para:
- Monitorear y optimizar el rendimiento de un sistema.
- Gestionar y asegurar el acceso a dispositivos y recursos hardware.
- Realizar tareas de mantenimiento y solución de problemas relacionados con hardware.


# Conteo de Islas

  ```C
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <stdbool.h>

#define FILAS 8
#define COLUMNAS 8

int mapa[FILAS][COLUMNAS];
bool visitados[FILAS][COLUMNAS];

int direccionX[4] = {-1, 1, 0, 0}; // Movimiento vertical (arriba y abajo)
int direccionY[4] = {0, 0, -1, 1}; // Movimiento horizontal (izquierda y derecha)

void inicializarVisitados() {
    for (int i = 0; i < FILAS; i++) {
        for (int j = 0; j < COLUMNAS; j++) {
            visitados[i][j] = false;
        }
    }
}

int obtenerNumeroAleatorio() {
    return rand() % 2; // Genera un número aleatorio entre 0 y 1
}

void imprimirMapa() {
    for (int i = 0; i < FILAS; i++) {
        for (int j = 0; j < COLUMNAS; j++) {
            printf("%d ", mapa[i][j]);
        }
        printf("\n");
    }
}

void llenarMapa() {
    for (int i = 0; i < FILAS; i++) {
        for (int j = 0; j < COLUMNAS; j++) {
            mapa[i][j] = obtenerNumeroAleatorio();
        }
    }
}

void realizarDFS(int x, int y) {
    visitados[x][y] = true;
    for (int i = 0; i < 4; i++) {
        int nuevoX = x + direccionX[i];
        int nuevoY = y + direccionY[i];

        if (nuevoX >= 0 && nuevoX < FILAS && nuevoY >= 0 && nuevoY < COLUMNAS && !visitados[nuevoX][nuevoY] && mapa[nuevoX][nuevoY] == 1) {
            realizarDFS(nuevoX, nuevoY);
        }
    }
}

int contarIslas() {
    int cantidadIslas = 0;
    inicializarVisitados();
    for (int i = 0; i < FILAS; i++) {
        for (int j = 0; j < COLUMNAS; j++) {
            if (mapa[i][j] == 1 && !visitados[i][j]) {
                realizarDFS(i, j);
                cantidadIslas++;
            }
        }
    }
    return cantidadIslas;
}

int main() {
    srand(time(NULL)); // Inicializa la semilla aleatoria
    llenarMapa(); // Llena el mapa con 0s y 1s aleatorios
    imprimirMapa(); // Muestra el mapa en la consola
    printf("Número de islas: %d\n", contarIslas()); // Muestra el total de islas
    return 0;
}


```
# Ejercicio de Recursividad
```C

#include <stdio.h>
#include <unistd.h>

int agregar(int x, int y);  
int expo(int x, int y) {
    if (y == 1) {
        return x;
    }
    if (y == 0) {
        return 1;
    }
    return agregar(x, expo(x, y - 1));  
}

int agregar(int x, int y) {
    if (y == 0) {
        return 0;
    }
    return x + agregar(x, y - 1);  
}

double divide(double n, double d) {
    double result = 0;

    if (d == 0) {
        printf("Error: no puedes dividir entre 0 tilin\n");
        return 0;
    }
    if (n == 0) {
        return 0;
    } else {
        result++;
    }
    return result + divide(n - d, d);  
}

int main(int argc, char **argv) {

    pid_t pid = fork();  

    if (pid < 0) {
        perror("El proceso no se creo correctamente");

    } else if (pid == 0) {
        printf("\nRecursive Division\n");
        double dvr = divide(500, 5);
        printf("%f\n", dvr);
        printf("Proceos hijito ID: %d\n", getpid());
    } else {
        printf("Recursive Exponentiation\n");
        int resultado = expo(5, 3);
        printf("%d\n", resultado);
        printf("Proceso padre ID: %d\n", getpid());
        printf("\n ------------------------------\n");
    }

    return 0;
}
```
# Cola prioridad

```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct NodoTarea {  
    char descripcion[50];
    int prioridad;
    struct NodoTarea* siguiente;
};

typedef struct ColaDePrioridades {  
    struct NodoTarea* cabeza;  
} ColaDePrioridades;

ColaDePrioridades* crearCola() {  
    ColaDePrioridades* cola = (ColaDePrioridades*)malloc(sizeof(ColaDePrioridades)); // 
    cola->cabeza = NULL;
    return cola;
}

 void agregarTarea(ColaDePrioridades* cola, char* descripcion, int prioridad) {
    struct NodoTarea* nuevaTarea = (struct NodoTarea*)malloc(sizeof(struct NodoTarea));
    strcpy(nuevaTarea->descripcion, descripcion);
    nuevaTarea->prioridad = prioridad;
    nuevaTarea->siguiente = NULL;

     if (cola->cabeza == NULL || cola->cabeza->prioridad < prioridad) {
        nuevaTarea->siguiente = cola->cabeza;
        cola->cabeza = nuevaTarea;
    } else {
        struct NodoTarea* actual = cola->cabeza;
         while (actual->siguiente != NULL && actual->siguiente->prioridad >= prioridad) {
            actual = actual->siguiente;
        }
        nuevaTarea->siguiente = actual->siguiente;
        actual->siguiente = nuevaTarea;
    }
}

char* eliminarTarea(ColaDePrioridades* cola, int* prioridad) {
    if (cola->cabeza == NULL) { 
        return NULL;
    }
    struct NodoTarea* temp = cola->cabeza;
    cola->cabeza = cola->cabeza->siguiente;

    *prioridad = temp->prioridad;
    char* descripcion = strdup(temp->descripcion);  
     free(temp);
    return descripcion;
}

char* obtenerTareaAlta(ColaDePrioridades* cola) {
     if (cola->cabeza == NULL) {
        return NULL;
    }
     return cola->cabeza->descripcion;
}

 int estaVacia(ColaDePrioridades* cola) {
    return cola->cabeza == NULL;
}

 void liberarCola(ColaDePrioridades* cola) {
    struct NodoTarea* actual = cola->cabeza;
    struct NodoTarea* siguiente;
    while (actual != NULL) {
        siguiente = actual->siguiente;
        free(actual);
        actual = siguiente;
    }
    free(cola);
}

int main() {
    ColaDePrioridades* cola = crearCola();

    agregarTarea(cola, "Tarea 1", 1);
    agregarTarea(cola, "Tarea 3", 5);
    agregarTarea(cola, "Tarea 2", 2);

    printf("Tarea de mayor prioridad: %s\n", obtenerTareaAlta(cola));

    int prioridad;
     while (!estaVacia(cola)) {
        
        char* tarea = eliminarTarea(cola, &prioridad);
        printf("Ejecutando: %s (Prioridad: %d)\n", tarea, prioridad);
         
        free(tarea);
    }

    liberarCola(cola);

    return 0;
}

```
# Administrador de memoria

```C
#include <stdio.h>
#include <stdbool.h>

#define TAM_MEM 10
bool hayProcesos = true;

int tamañoParticiones = 0;
typedef struct bloqueMemoria {
    int PID;
    int tamaño;
} bloqueMemoria;

bloqueMemoria memoria[TAM_MEM];

void crearParticiones() {
    int sumaParticiones = 0;
    int tamañoTemp = 0;
    int contador = -1;
    
    if (tamañoParticiones > TAM_MEM) {
        printf("Las particiones exceden el espacio total de memoria disponible.\n");
        return;
    }

    for (int i = 0; i < tamañoParticiones; i++) {
        contador++;

        if (sumaParticiones >= TAM_MEM) {
            printf("Memoria llena, no se pueden asignar más particiones.\n");
            tamañoParticiones = contador;
            break;
        }

        do {
            printf("Ingrese el tamaño de la partición %d (MB): ", (i + 1));
            scanf("%d", &tamañoTemp);

            if (sumaParticiones + tamañoTemp > TAM_MEM) {
                printf("Error: La partición excede el tamaño total de memoria (%d MB).\n", TAM_MEM);
                printf("Espacio restante disponible: %d MB.\n", TAM_MEM - sumaParticiones);
            } else {
                memoria[i].PID = -1;
                memoria[i].tamaño = tamañoTemp;
                sumaParticiones += tamañoTemp;
                break;
            }
        } while (true);
    }
    printf("\n");
}

bool estaMemoriaLlenada() {
    for (int i = 0; i < tamañoParticiones; i++) {
        if (memoria[i].PID == -1) {
            return false;
        }
    }
    return true;
}

bool verificarPID(int pid) {
    for (int i = 0; i < tamañoParticiones; i++) {
        if (memoria[i].PID == pid && pid >= 0) {
            return true;
        }
    }
    return false;
}

void asignarMemoria() {
    int pid;
    int tamañoProceso;
    int espacioRestante;
    int asignado = 0;
    
    printf("Ingrese el ID de proceso: ");
    scanf("%d", &pid);

    if (verificarPID(pid)) {
        printf("Este PID ya está en uso o no es válido.\n");
        return;
    }

    printf("Ingrese el tamaño del proceso (MB): ");
    scanf("%d", &tamañoProceso);

    for (int i = 0; i < tamañoParticiones; i++) {
        if (estaMemoriaLlenada()) {
            printf("Memoria llena, no hay más particiones disponibles.\n");
            return;
        }

        if (memoria[i].PID == -1 && memoria[i].tamaño >= tamañoProceso) {
            memoria[i].PID = pid;
            printf("\nProceso %d asignado a la partición %d\n", pid, i + 1);
            espacioRestante = memoria[i].tamaño - tamañoProceso;
            printf("Espacio desperdiciado: %d MB\n", espacioRestante);
            asignado = 1;
            break;
        }
    }
    if (asignado == 0) {
        printf("No se encontró una partición adecuada para este proceso.\n");
    }
    printf("\n");
}

void liberarMemoria() {
    int pidEliminado = 0;
    bool encontrado = false;
    
    printf("Seleccione el proceso a eliminar (PID): ");
    scanf("%d", &pidEliminado);

    for (int i = 0; i < tamañoParticiones; i++) {
        if (pidEliminado == memoria[i].PID) {
            memoria[i].PID = -1;
            printf("Proceso con PID %d eliminado de la partición %d.\n", pidEliminado, i + 1);
            encontrado = true;
            break;
        }
    }
    if (!encontrado) {
        printf("No se encontró un proceso con PID %d.\n", pidEliminado);
    }
}

void mostrarMemoria() {
    bool procesosMostrados = true;
    for (int i = 0; i < tamañoParticiones; i++) {
        if (memoria[i].PID != -1) {
            printf("PID: %d  Partición: %d  Tamaño de partición: (%d MB)\n", memoria[i].PID, i + 1, memoria[i].tamaño);
            procesosMostrados = false;
        } else if (memoria[i].tamaño > 0) {
            printf("Partición %d libre\n", i + 1);
        }
    }

    if (procesosMostrados) {
        printf("No hay procesos para mostrar.\n");
        hayProcesos = false;
    }
}

int main() {
    int opcion = 0;
    do {
        printf("1.- Crear particiones\n");
        printf("2.- Asignar espacio de memoria\n");
        printf("3.- Liberar espacio de memoria\n");
        printf("4.- Mostrar particiones y procesos\n");
        printf("5.- Salir\n");
        scanf("%d", &opcion);
        
        switch (opcion) {
            case 1:
                printf("Ingrese el número máximo de particiones: ");
                scanf("%d", &tamañoParticiones);
                crearParticiones();
                break;

            case 2:
                asignarMemoria();
                break;

            case 3:
                mostrarMemoria();
                if (hayProcesos) {
                    liberarMemoria();
                }
                break;

            case 4:
                mostrarMemoria();
                break;

            case 5:
                return 0;

            default:
                printf("Opción no válida.\n");
        }
    } while (true);
    
    return 0;
}
```

# Prueba de escritorio Dekker

 
| C | Hilo      | Acción                               | Interesado  | Turno | Cabeza   | Output                            |
|---|-----------|--------------------------------------|-------------|-------|----------|-----------------------------------|
| 0 | Productor | Interesado[0] = 1                   | [1, 0]      | 0     | NULL     |                                   |
|   |           | While (Interesado[1] == False)      | [1, 0]      | 0     | NULL     |                                   |
|   |           | InsertarFinal(i+1)                  | [1, 0]      | 0     | [1] -> NULL | Productor produjo 1              |
|   |           | Interesado[0] = 0                   | [0, 0]      | 0     | [1] -> NULL |                                   |
|   |           | Sleep(1)                            | [0, 0]      | 0     | [1] -> NULL |                                   |
|   | Consumidor| Interesado[1] = 1                   | [0, 1]      | 0     | [1] -> NULL |                                   |
|   |           | While (Interesado[0] == False)      | [0, 1]      | 0     | [1] -> NULL |                                   |
|   |           | AtenderProceso(i = Free(temp))      | [0, 1]      | 0     | NULL     | Consumidor atendió 1             |
|   |           | Turno = 0                           | [0, 1]      | 0     | NULL     |                                   |
|   |           | Interesado[1] = 0                   | [0, 0]      | 0     | NULL     |                                   |
|   |           | Sleep(1)                            | [0, 0]      | 0     | NULL     |                                   |
| 1 | Productor | Interesado[1] = 1                   | [0, 1]      | 0     | NULL     |                                   |
|   | Consumidor| Interesado[0] = 1                   | [1, 1]      | 0     | NULL     |                                   |
|   |           | While (Interesado[1] == True)       | [1, 1]      | 0     | NULL     |                                   |
|   |           | If(Turno != 0)                      | [1, 1]      | 0     | NULL     |                                   |
|   |           | Espera                              | [1, 1]      | 0     | NULL     |                                   |
|   |           | Interesado[1] = 0                   | [1, 0]      | 0     | NULL     |                                   |
|   |           | InsertarFinal(i+1)                  | [1, 0]      | 0     | [2] -> NULL | Productor produjo 2              |
|   |           | While (Turno == True) (ciclo)       | [1, 0]      | 0     | [2] -> NULL |                                   |
|   |           | Turno = 1                           | [1, 0]      | 1     | [2] -> NULL |                                   |
|   |           | Interesado[1] = 1                   | [1, 1]      | 1     | [2] -> NULL |                                   |
|   |           | Interesado[0] = 0                   | [0, 1]      | 1     | [2] -> NULL |                                   |
|   |           | AtenderProceso / salir ciclo        | [0, 1]      | 1     | NULL     | Consumidor atendió 2             |
|   |           | Sleep(1)                            | [0, 1]      | 1     | NULL     |                                   |
|   |           | Turno = 0                           | [0, 1]      | 0     | NULL     |                                   |
|   |           | Interesado[0] = 1                   | [1, 1]      | 0     | NULL     |                                   |
|   |           | Interesado[1] = 1                   | [1, 1]      | 0     | NULL     |                                   |
 
# Prueba de escritorio Peterson

 
| C | Hilo      | Acción                                  | Interesado | Turno | Cabeza   | Output                             |
|---|-----------|-----------------------------------------|------------|-------|----------|------------------------------------|
| 0 | Productor | Interesado[0] = 1                      | [1, 0]     | 0     | NULL     |                                    |
|   | Consumidor| Interesado[1] = 1                      | [1, 1]     | 0     | NULL     |                                    |
|   | Productor | Turno = 1                              | [1, 1]     | 1     | NULL     |                                    |
|   | Consumidor| Turno = 0                              | [1, 1]     | 0     | NULL     |                                    |
|   |           | While (Interesado[0] and Turno == 0)   | [1, 1]     | 0     | NULL     |                                    |
| P |           | While (Interesado[0] and Turno == 0)   | [1, 1]     | 0     | NULL     |                                    |
| P |           | GeneraProceso(i+1)                    | [1, 1]     | 0     | [1] -> NULL | Productor generó 1                 |
|   |           | Espera                                 | [1, 1]     | 0     | [1] -> NULL |                                    |
|   |           | Interesado[0] = 0                      | [0, 1]     | 0     | [1] -> NULL |                                    |
| C |           | AtiendeProceso(Free(temp))             | [0, 1]     | 0     | NULL     | Consumidor atendió 1               |
|   |           | Sleep(1)                               | [0, 1]     | 0     | NULL     |                                    |
| 2 | Productor | Interesado[0] = 1                      | [1, 1]     | 0     | NULL     |                                    |
|   |           | Espera (while)                         | [1, 1]     | 0     | NULL     |                                    |
|   |           | Turno = 0                              | [1, 1]     | 0     | NULL     |                                    |
|   |           | GeneraProceso(i+1)                    | [1, 1]     | 0     | [2] -> NULL | Productor generó 2                 |
|   |           | Espera                                 | [1, 1]     | 0     | [2] -> NULL |                                    |
|   |           | Interesado[0] = 0                      | [0, 1]     | 0     | [2] -> NULL |                                    |
| C |           | AtiendeProceso(Free(temp))             | [0, 1]     | 0     | NULL     | Consumidor atendió 2               |
|   |           | Sleep(1)                               | [0, 1]     | 0     | NULL     |                                    |
| 3 | Productor | Interesado[0] = 1                      | [1, 1]     | 0     | NULL     |                                    |
|   |           | Interesado[1] = 1                      | [1, 1]     | 0     | NULL     |                                    |
|   |           | Sleep(1)                               | [1, 1]     | 0     | NULL     |                                    |
|   |           | Turno = 1                              | [1, 1]     | 1     | NULL     |                                    |
| C |           | Interesado[1] = 1                      | [1, 1]     | 1     | NULL     |                                    |
|   |           | Espera                                 | [1, 1]     | 1     | NULL     |                                    |
| P |           | Turno = 0                              | [1, 1]     | 0     | NULL     |                                    |
| P |           | GeneraProceso(i+1)                    | [1, 1]     | 0     | [3] -> NULL | Productor generó 3                 |
 
