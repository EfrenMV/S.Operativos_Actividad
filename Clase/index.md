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
