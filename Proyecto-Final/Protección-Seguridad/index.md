<!--Portada-->
<div align="center">

# Sistemas Operativos

### Proyecto Final<br>Protección y Seguridad

### ISC

### Docente: Jesus Eduardo Alacaraz Chavez

### Alumno: Efren Mendez Villanueva

</div>

___

# Índice
- [Ejercicio 1 Concepto y objetivos de protección y seguridad ](#ejericio-1-concepto-y-objetivos-de-protección-y-seguridad)
  - [Define el concepto de archivo real y archivo virtual:](#define-el-concepto-de-archivo-real-y-archivo-virtual)
  - [Proporciona ejemplo de como los sistemas operativos manejan archivos reales y virtuales:](#proporciona-ejemplo-de-cómo-los-sistemas-operativos-manejan-archivos-reales-y-virtuales)
  - [Explica un caso practico donde un archivo virtual sea mas útil que un archivo real:](#explica-un-caso-practico-donde-un-archivo-virtual-sea-mas-útil-que-un-archivo-real)
- [Ejercicio 2 Clasificación aplicada a la seguridad](#ejercicio-2-clasificación-aplicada-a-la-seguridad)
  - [Investiga las clasificaciones comunes de la seguridad, como física, lógica y de red](#investiga-las-clasificaciones-comunes-de-la-seguridad-como-física-lógica-y-de-red)
  - [Explica el papel de cada clasificación en la protección de un sistema operativo](#explica-el-papel-de-cada-clasificación-en-la-protección-de-un-sistema-operativo)
  - [Proporciona ejemplos prácticos de herramientas o técnicas utilizadas en cada clasificación](#proporciona-ejemplos-prácticos-de-herramientas-o-técnicas-utilizadas-en-cada-clasificación)
- [Ejercicio 3 Funciones del sistema de protección](#ejercicio-3-funciones-del-sistema-de-protección)
  - [Describe cómo un sistema de protección controla el acceso a los recursos](#describe-cómo-un-sistema-de-protección-controla-el-acceso-a-los-recursos)
  - [explica las funciones principales como autenticación, autorización y auditoría.](#explica-las-funciones-principales-como-autenticación-autorización-y-auditoría)
  - [Sub-sección 2.1](#sub-sección-21)
- [Ejercicio 4 Implantación de matrices de acceso.](#ejercicio-4-implantación-de-matrices-de-acceso)
  - [Diseña una matriz de acceso para un sistema con al menos 3 usuarios y 4 recursos.](#diseña-una-matriz-de-acceso-para-un-sistema-con-al-menos-3-usuarios-y-4-recursos)
  - [Explica cómo esta matriz se utiliza para controlar el acceso en un sistema operativo.](#explica-cómo-esta-matriz-se-utiliza-para-controlar-el-acceso-en-un-sistema-operativo)
  - [Simula un escenario donde un usuario intena acceder a un recurso no permitido y cómo la matriz lo bloquea.](#simula-un-escenario-donde-un-usuario-intena-acceder-a-un-recurso-no-permitido-y-cómo-la-matriz-lo-bloquea)
- [Ejercicio 5 Protección basada en el lenguaje](#ejercicio-5-protección-basada-en-el-lenguaje)
  - [Explica el concepto de protección basado en el lenguaje.](#explica-el-concepto-de-protección-basado-en-el-lenguaje)
  - [Proporciona un ejemplo de cómo un lenguaje como Java o Rust asegura la memoria y evita de acceso no autorizados.](#proporciona-un-ejemplo-de-cómo-un-lenguaje-como-java-o-rust-asegura-la-memoria-y-evita-de-acceso-no-autorizados)
  - [Compara este enfoque con otros mecanismos de protección en sistemas operativos.](#compara-este-enfoque-con-otros-mecanismos-de-protección-en-sistemas-operativos)
- [Ejercicio 6](#ejercicio-6-validación-y-amenazas-al-sitema)
  - [Investiga y describe al menos tres tipos de amenazas comunes ( por ejemplo, malware, ataques de fuerza bruta, inyección de código).](#investiga-y-describe-al-menos-tres-tipos-de-amenazas-comunes--por-ejemplo-malware-ataques-de-fuerza-bruta-inyección-de-código)
  - [Explica los mecanismos de validación como autenticación multifacor y control de integridad.](#explica-los-mecanismos-de-validación-como-autenticación-multifacor-y-control-de-integridad)
  - [Diseña un esquema de validación para un sistema operativo con múltiples usuarios.](#diseña-un-esquema-de-validación-para-un-sistema-operativo-con-múltiples-usuarios)
- [Ejercicio 7 Cifrado](#ejercicio-7-cifrado)
  - [Define los conceptos de cifrado simétrico y asimétrico.](#define-los-conceptos-de-cifrado-simétrico-y-asimétrico)
  - [Proporciona un ejemplo práctico de cada tipo de cifrado aplicado en sistemas operativos.](#proporciona-un-ejemplo-práctico-de-cada-tipo-de-cifrado-aplicado-en-sistemas-operativos)
  - [Simula el proceso de cifrado y descifrado de un archivo con una clave dada.](#simula-el-proceso-de-cifrado-y-descifrado-de-un-archivo-con-una-clave-dada)

# Ejericio 1: Concepto y objetivos de protección y seguridad
## Tareas:
### Define los conceptos de protección y seguridad en el contexto de sistemas operativos

**Protección:** 

Son las medidas y mecanismos que garantizan que los recursos del sistema (como la memoria, los procesos y los arhcivos) sean accedidos solo por aquellos
usuarios o proceso que tengan permisos edecudados. Esta proteccion busca evitar que los procesos o usaurios accedan o modifiquen datos o recursos que no les corresponden. Está relacionada
con el control de acceso dentro de un sistema operativos

* **Control de acceso:** Permite que solo los usuarios o procesos autorizados puedan acceder a los recursos del sistema.
* **Aislamiento de procesos:** Los procesos deben ejecutarse en un espacio de memoria aislado para que no puedan interferir o acceder a la memoria de otros proceos sin permiso.
* **Gestión de privilegios:** Controlar qué acciones pueden realizar los usuarios o procesos (lectura, escritura, ejecución) sobre los recursos del sistema.


**Seguridad en sisteams Operativos:**

Son las medidas y mecanismos implementados para proteger un sistema contra amenazas externas e internas, como ataques maliciosos, acceso no autorizados o destrucción de datos. En este contexto, la seguirdad no solo ocupa de control el acceso, sino también de proteger el sistema frente a actividades malicioso que pueden comprometer su funcionamiento. 

Algunos aspectos clave de la seguridad incluyen:

* Autenticación  
* Autorización 
* Confidencialidad 
* Integridad 
* Auditoría y monitoreo 

### Indentifica los objetivos principales de un sistema de protección y seguridad, como confidencialidad, integridad y disponibilidad.

Objetivos principales en un sistemas de protección y seguridad 

**Confidencialidad:** 

Este se refiere a la protección de la información contra acceso no autorizados. EL objetivo es asegurarse de que solo las personas o entidades que tienen los primisos adecuados pueden acceder a la información, Si la confidencialidad no se garantiza, los datos sensibles pueden ser expuestos a usuarios no autorizados, lo que podría resultar en violaciones de privacidad o el robo de información crítica. 


**Integridad**

Esto asegura que la información no sea alterada de manera no autorizada, ya sea de forma accidental o maliciosa. Esto implica que los datos deben permanecer completos, precisos y confiables a lo largo del tiempo. Un sistema con buena integridad detecta y previene la modificación no autorizada de los datos y asegura que los datos sean correctos en todo momento. 

**Disponibilidad**

EGarantiza que los recursos del sistema (como datos, aplicaciones y servicios ) estén accesibles y funcionado cuando los usuarios autorizados lo necesiten. Un sistema con alta diponibilidad es capaz de mantener sus operaciones a pesar de fallos del sistema, ataques o problemas de infraestructura. La disponibilidad es crucial para asegurar que los usuarios puedan acceder a los recursos en tiempo real sin interrupciones. 

### Da un ejemplo práctico de cómo se aplican estos objetivos en un sistema operativo

Nada

# Ejercicio 2: Clasificación aplicada a la seguridad
## Tareas:
### Investiga las clasificaciones comunes de la seguridad, como física, lógica y de red

Clasificacion comunes de la seguridad 

**Fisica:**

Este se refiere a las medidas de protección que s eimplementan para salvaguardar el hardware y los recursos fisicos de una organización frente a ccesos no autorizados, daños, robo o destrucción.

**Logica:**

Son las medidas que se toman para proteger los sistemas de información a nivel de software y procesos informáticos


**Red:**

Refiere a la proteccion de los sistemas y dispositivos interconectados a través de una red de comunicaciones, con el objetivo de garantizar que los datos que circulan por ella sean confidenciales, integros y estén disponibles cuando se necesiten,. Esta seguridad incluye medidas para proteger tanto la infraestructura de red como el trafico de datos que fluye a través de ella.

### Explica el papel de cada clasificación en la protección de un sistema operativo

**Papel de la seguridad Fisica**

* **Proteger al servidor y sus dispositivos:** discos y otros componentes de hardware deben estar protegidos fisicamente para evitar daños.

* **Prevención de desastres:** Estar preparados para desastres como incendios, inundaciones etc.

* **Accesp controlado a centros de datos:** Los servidores deben de tener controles de acceso físico (Cerraduras, sistemas biométricos, cámaras de vigilancia etc..).

**Seguridad Lógica**

* **Control de acceso a recursos:** Para garantizar que los usuarios o proceos autorizados puedan aceder a modificar recursos del sistema.

* **Aislamiento de proceso:** Hacer que los procesos no interfieran entre ellos, teniendolos aislados.

* **Prevención de modificaciones no autorizadas:** Para evitar la alteración del sistema operativo o de sus archivos criticos. Esto mediante medidas como el uso de firmas digitales.

* **Auditoría y monitereo:** Poder realizar auditoría de las actividades de los usuarios y los procesos. 

**Papel de la seguridad de red**

* **Protección del tráfico de datos:** Garantizar que los datos que se transmiten no puedan ser interceptados, modificados o robados.

* **Defensa contra ataques externos:** Poder resistir a ataques provenientes de redes externas, como DDos.

* **Aislamiento de redes y segmentación:** El S.O debe ser capaz de controlar el acceso a redes internas y externas.

### Proporciona ejemplos prácticos de herramientas o técnicas utilizadas en cada clasificación

# Ejercicio 3: Funciones del sistema de protección
## Tareas:
### Describe cómo un sistema de protección controla el acceso a los recursos

1. Mecanismos de Control de Acceso
Los mecanismos de control de acceso son las herramientas y técnicas utilizadas para implementar las políticas de seguridad que dictan quién puede acceder a qué recursos y bajo qué condiciones. Los principales mecanismos incluyen:

  * a) Autenticación 
      La autenticación es el proceso de verificar la identidad de un usuario o proceso que solicita acceso a un recurso del sistema. El objetivo es asegurarse de que el solicitante es quien dice ser.

  * b) Autorización
      Una vez que un usuario o proceso ha sido autenticado, el sistema verifica si tiene permiso para acceder al recurso solicitado. La autorización determina qué acciones pueden realizar los usuarios autenticados en función de sus privilegios.

 
    * c) Acceso a Recursos Físicos y Lógicos
      Un sistema de protección también puede restringir el acceso a recursos físicos (hardware) y lógicos (software), mediante mecanismos adicionales.

2. Políticas de Protección
Las políticas de protección definen las reglas que gobiernan cómo se conceden y gestionan los permisos de acceso a los recursos. Estas políticas aseguran que el acceso a los recursos se realice de manera controlada y conforme a las necesidades de seguridad del sistema.

  * a) Política de Menor Privilegio
      La política de menor privilegio establece que los usuarios y procesos deben tener solo los permisos estrictamente necesarios para realizar sus tareas, evitando que tengan acceso innecesario a otros recursos que no sean relevantes para su funcionamiento. Esto reduce la superficie de ataque y mitiga los daños en caso de que un proceso sea comprometido.

  * b) Política de Necesidad de Saber
      Relacionado con la política de menor privilegio, la política de necesidad de saber restringe el acceso a información confidencial o sensible solo a aquellos usuarios o procesos que realmente necesiten acceder a esa información para realizar su trabajo. Por ejemplo, un empleado de ventas no debería tener acceso a la base de datos de finanzas.

  * c) Política de Control de Acceso Condicional
      En algunos casos, el acceso a recursos puede estar condicionado por ciertas circunstancias, como el tiempo del día, la ubicación, o el tipo de dispositivo desde el que se accede. Esto se puede implementar mediante sistemas de autenticación multifactor o gestión de acceso basada en contexto.

3. Manejo de Roles y Permisos
El sistema de protección también gestiona los roles de los usuarios y los permisos asociados a esos roles. Los permisos son asignados a los roles, y luego los usuarios se agrupan en roles que tienen ciertos derechos sobre los recursos. Esto simplifica la administración de acceso.


4. Auditoría y Monitoreo de Acceso
La auditoría y el monitoreo son funciones clave de un sistema de protección para asegurar que los recursos sean utilizados de acuerdo con las políticas de acceso. Permiten detectar y registrar cualquier intento de acceso no autorizado o actividad sospechosa.

### Explica las funciones principales como autenticación, autorización y auditoría.
**Autenticación:**

Proceos mediante el cual un sistema verifica la identidad de un usuario o proceso que intenta aceder a un recurso o servicio.

**Autorización:**

Proceso que ocurre después de la autentificación. Una vez que se ha verificado la indentidad de un usuario

**Auditoría:**

Proceso que registra y analiza las actividades que ocurren dentro de un sistema para poder realizar un seguimiento a las acciones de los usuarios.

# Ejercicio 4: Implantación de matrices de acceso
## Tareas:
### Diseña una matriz de acceso para un sistema con al menos 3 usuarios y 4 recursos.
# Matriz de Acceso para un Sistema con 3 Usuarios y 4 Recursos

La **matriz de acceso** es una estructura que se utiliza para controlar y gestionar el acceso a recursos por parte de los usuarios en un sistema operativo. En esta matriz, cada fila representa un **usuario**, cada columna representa un **recurso**, y las celdas indican los **permisos** que cada usuario tiene sobre cada recurso.

Imaginemos un sistema con 3 usuarios y 4 recursos. Los recursos pueden ser archivos, dispositivos o cualquier otro objeto gestionado por el sistema operativo. A continuación se muestra un ejemplo de la matriz de acceso:

|           | Recurso 1 | Recurso 2 | Recurso 3 | Recurso 4 |
|-----------|-----------|-----------|-----------|-----------|
| **Usuario 1** | Lectura, Escritura | Lectura | Ningún acceso | Lectura, Escritura |
| **Usuario 2** | Ningún acceso | Lectura | Lectura, Escritura | Ningún acceso |
| **Usuario 3** | Lectura | Ningún acceso | Lectura | Lectura |

---
 
### Explica cómo esta matriz se utiliza para controlar el acceso en un sistema operativo.


**Explicación de la Matriz de Acceso**

- **Usuarios**: Las filas de la matriz representan a los usuarios del sistema.
  - **Usuario 1, Usuario 2, Usuario 3**: Son los diferentes usuarios del sistema.
- **Recursos**: Las columnas representan los recursos disponibles en el sistema.
  - **Recurso 1, Recurso 2, Recurso 3, Recurso 4**: Estos son los recursos a los que los usuarios intentan acceder, como archivos, impresoras, o dispositivos.
- **Permisos**: Los permisos que los usuarios tienen sobre cada recurso están definidos en las celdas. Los permisos más comunes son:
  - **Lectura**: El usuario puede ver el contenido del recurso.
  - **Escritura**: El usuario puede modificar el contenido del recurso.
  - **Ningún acceso**: El usuario no tiene permisos para interactuar con el recurso.

**Utilización de la Matriz para Controlar el Acceso**

El sistema operativo utiliza la matriz de acceso para verificar si un usuario tiene permisos para acceder a un recurso específico. Cada vez que un usuario solicita acceder a un recurso, el sistema operativo consulta la matriz para verificar si el usuario tiene los permisos adecuados para realizar la operación solicitada.

**Pasos del proceso:**

1. **Petición de acceso**: Un usuario solicita acceso a un recurso, especificando la operación que desea realizar (lectura, escritura, etc.).
2. **Verificación en la matriz**: El sistema operativo verifica en la matriz de acceso si el usuario tiene el permiso correspondiente sobre el recurso solicitado.
3. **Decisión del sistema**:
   - Si el permiso está presente, se permite la operación.
   - Si el permiso no está presente, se bloquea la operación y se genera un mensaje de error o una acción de denegación.


### Simula un escenario donde un usuario intena acceder a un recurso no permitido y cómo la matriz lo bloquea.


 **Escenario de Simulación: Usuario Intentando Acceder a un Recurso No Permitido**


**Escenario**: Imaginemos que el **Usuario 2** intenta escribir en el **Recurso 1**. Según la matriz, el **Usuario 2** no tiene permiso de escritura en el **Recurso 1**; solo tiene acceso de lectura.

|           | Recurso 1 | Recurso 2 | Recurso 3 | Recurso 4 |
|-----------|-----------|-----------|-----------|-----------|
| **Usuario 1** | Lectura, Escritura | Lectura | Ningún acceso | Lectura, Escritura |
| **Usuario 2** | Ningún acceso | Lectura | Lectura, Escritura | Ningún acceso |
| **Usuario 3** | Lectura | Ningún acceso | Lectura | Lectura |

**Paso 1: Usuario 2 solicita acceso a Recurso 1**

Usuario 2 intenta realizar una operación de **escritura** en el **Recurso 1**.

**Paso 2: Verificación en la Matriz**

El sistema operativo consulta la matriz para verificar los permisos de **Usuario 2** sobre **Recurso 1**. En la matriz, se observa que en la intersección de **Usuario 2** y **Recurso 1**, no hay ningún acceso (la celda está vacía, lo que indica que no tiene permisos).

**Paso 3: Denegación del acceso**

Como el **Usuario 2** no tiene permiso de **escritura** en el **Recurso 1**, el sistema operativo bloquea la operación y genera un mensaje de error, por ejemplo: 
- "Acceso denegado: El usuario no tiene permisos para escribir en este recurso."

**Paso 4: Mensaje de Error**

El usuario recibe un mensaje de error que le informa sobre la falta de permisos para realizar la operación solicitada.


# Ejercicio 5: Protección basada en el lenguaje
## Tareas:
### Explica el concepto de protección basado en el lenguaje.

Se refiere al uso de lenguajes de programación y sus características para proporcionar mecanismos de seguridad y control de acceso en un sistema operativo o aplicación. Esta forma de protección está diseñada para garantizar que los programas y los usuarios solo puedan realizar las acciones para las cuales están autorizados, reduciendo así el riesgo de errores o de actividades maliciosas que comprometan la integridad, confidencialidad o disponibilidad de los recursos del sistema.

### Proporciona un ejemplo de cómo un lenguaje como Java o Rust asegura la memoria y evita de acceso no autorizados.

**Ejemplo de Protección de Memoria en Java**

Java utiliza la máquina virtual de Java (JVM) para ejecutar aplicaciones, lo que permite un aislamiento de memoria entre los programas y el sistema operativo. A través de su diseño y de las características del lenguaje, Java puede permitir por ejemplo la siguiente manera de protección de memoria:

* **Gestión Automática de Memoria (Garbage Collection):**
Java no permite a los desarrolladores manejar directamente la memoria (por ejemplo, mediante punteros), lo que reduce significativamente los riesgos de errores de memoria como los desbordamientos de búfer o el acceso a memoria no válida. La recolección de basura (garbage collection) se encarga de liberar la memoria ocupada por objetos que ya no son accesibles, lo que previene fugas de memoria y errores de acceso a memoria.

### Compara este enfoque con otros mecanismos de protección en sistemas operativos

# Ejercicio 6: Validación y amenazas al sitema 
## Tareas: 
### Investiga y describe al menos tres tipos de amenazas comunes ( por ejemplo, malware, ataques de fuerza bruta, inyección de código).

| **Amenaza**                | **Descripción**                                                                                                                                                        | **Impacto en el sistema**                                                         | **Medidas de protección**                                                                                   |
|----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Malware**                 | Software malicioso que daña, roba o compromete sistemas. Incluye virus, troyanos, ransomware, spyware, etc.                                                             | Puede destruir datos, robar información, controlar sistemas remotamente.         | Uso de antivirus, actualización constante de software, técnicas de detección proactiva de malware.           |
| **Ataques de Fuerza Bruta** | Intentos automatizados de adivinar contraseñas probando todas las combinaciones posibles.                                                                             | Compromiso de contraseñas y acceso a cuentas de usuario.                         | Uso de contraseñas fuertes, autenticación multifactor, limitación de intentos de inicio de sesión.           |
| **Inyección de Código**     | Inserción de código malicioso en aplicaciones o bases de datos con el fin de ejecutar comandos no autorizados.                                                           | Acceso a bases de datos, ejecución remota de código, robo de información.        | Validación y escape de entradas, uso de consultas preparadas (SQL), restricciones de permisos en sistemas. |

### Explica los mecanismos de validación como autenticación multifacor y control de integridad.

1. **Autenticación Multifactor (MFA)**
    
    La autenticación multifactor (MFA) es un mecanismo de seguridad que requiere que los usuarios proporcionen dos o más factores de verificación antes de acceder a un sistema o recurso. El objetivo de MFA es agregar capas adicionales de protección para reducir el riesgo de que un atacante obtenga acceso a una cuenta o sistema, incluso si conoce la contraseña.

Factores de Autenticación
Los factores de autenticación generalmente se dividen en tres categorías principales:

  * **Conocimiento:** Algo que sabes. 
  * **Posesión:** Este es el factor más común y generalmente es una contraseña o un PIN. Es algo que solo el usuario debe conocer.
    Algo que tienes.
  * **Biometria:** Un dispositivo o medio físico que el usuario posee. Ejemplos comunes incluyen tarjetas de seguridad, tokens de hardware (como llaves USB), o un teléfono móvil que recibe un código a       travé  de SMS o aplicaciones de autenticación.
    Algo que eres 
 
2. **Control de Integridad**

El control de integridad es un mecanismo que asegura que los datos no sean alterados, manipulados o corrompidos, ya sea de manera intencional o accidental. En el contexto de la seguridad informática, la integridad se refiere a la exactitud, consistencia y confiabilidad de los datos.

**Checksums:** Mecanismos Comunes de Control de Integridad
Sumas de Verificación 

Las **sumas de verificación** son valores calculados a partir de un conjunto de datos. Si los datos se alteran, la suma de verificación cambiará. Este método se usa para verificar que los datos no han sido modificados.

**Firmas Digitales**

Las firmas digitales son una forma avanzada de control de integridad que utiliza criptografía para asegurar que los datos no hayan sido modificados y provienen de una fuente autenticada. Una firma digital es creada usando una clave privada y puede ser verificada con una clave pública.


**Hashing Criptográfico**

El hashing es un proceso que toma un bloque de datos de cualquier tamaño y lo convierte en un valor de tamaño fijo (el hash). Si los datos son modificados, el hash resultante cambiará, lo que indica que la integridad de los datos ha sido comprometida.

**Detección de manipulaciones:** 

Permite identificar si los datos han sido modificados, ya sea de manera accidental o maliciosa.
Seguridad en la transmisión de datos: Protege la integridad de los datos durante la transmisión a través de redes no confiables, como internet.
Protección contra ataques: Previene ataques como la modificación de datos en tránsito o la suplantación de mensajes.

**Dependencia de claves secretas:**

En algunos métodos de control de integridad, como el uso de MACs o firmas digitales, la seguridad depende de mantener las claves privadas de manera segura.
Sobrecarga de procesamiento: Los procesos de hashing y verificación de integridad pueden agregar una carga computacional adicional, especialmente en sistemas con grandes volúmenes de datos.

### Diseña un esquema de validación para un sistema operativo con múltiples usuarios.

# Ejercicio 7: Cifrado
## Tareas:
### Define los conceptos de cifrado simétrico y asimétrico.

**Cigrado Simétrico:**

 Se utiliza la misma clave tanto para cifrar como para descifrar los datos. Es rápido y eficiente, pero requiere que ambas partes (quien cifra y quien descifra) compartan la misma clave secreta de manera segura.

### Proporciona un ejemplo práctico de cada tipo de cifrado aplicado en sistemas operativos.

Supongamos que en un sistema operativo, un usuario quiere cifrar un archivo de texto para almacenarlo de forma segura. El sistema utilizaría una clave secreta para cifrar el archivo con AES, y solo alguien que tenga esa misma clave secreta podría descifrarlo.


### Simula el proceso de cifrado y descifrado de un archivo con una clave dada.

