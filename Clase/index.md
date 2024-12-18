<div align="center">

# Sistemas Operativos

### Proyecto Final<br>Actividades en clase

### ISC

### Docente: Jesus Eduardo Alacaraz Chavez

### Alumno: Efren Mendez Villanueva

</div>

___
 
# Índice
- [Fibonacci](#fibonacci)
  - [Potencia_Suma](#potencia_suma)
  - [Divición_Resta](#divición_resta)
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
