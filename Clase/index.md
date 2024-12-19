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
