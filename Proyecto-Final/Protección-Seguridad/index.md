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
  - [Proporciona ejemplos prácticos de herramientas o técnicas utilizadas en cada clasificación](#proporciona-ejemplos-prácticos-de-herramientas-o-técnicas-utilizadas-en-cada-clasificación
- [Ejercicio 3 Funciones del sistema de protección](#ejercicio-3-funciones-del-sistema-de-protección)
  - [Describe cómo un sistema de protección controla el acceso a los recursos](#describe-cómo-un-sistema-de-protección-controla-el-acceso-a-los-recursos)
  - [explica las funciones principales como autenticación, autorización y auditoría.](#explica-las-funciones-principales-como-autenticación-autorización-y-auditoría)
  - [Sub-sección 2.1](#sub-sección-21)
- [Ejercicio 4 Implantación de matrices de acceso](#ejercicio-4-implantación-de-matrices-de-acceso)
  - [Diseña una matriz de acceso para un sistema con al menos 3 usuarios y 4 recursos.](#diseña-una-matriz-de-acceso-para-un-sistema-con-al-menos-3-usuarios-y-4-recursos)
  - [Explica cómo esta matriz se utiliza para controlar el acceso en un sistema operativo.](#explica-cómo-esta-matriz-se-utiliza-para-controlar-el-acceso-en-un-sistema-operativo)
  - [Simula un escenario donde un usuario intena acceder a un recurso no permitido y cómo la matriz lo bloquea.](#simula-un-escenario-donde-un-usuario-intena-acceder-a-un-recurso-no-permitido-y-cómo-la-matriz-lo-bloquea)
- [Ejercicio 5 Protección basada en el lenguaje](#ejercicio-5-protección-basada-en-el-lenguaje)
  - [Explica el concepto de protección basado en el lenguaje.](#explica-el-concepto-de-protección-basado-en-el-lenguaje)
  - [Proporciona un ejemplo de cómo un lenguaje como Java o Rust asegura la memoria y evita de acceso no autorizados.](#proporciona-un-ejemplo-de-cómo-un-lenguaje-como-java-o-rust-asegura-la-memoria-y-evita-de-acceso-no-autorizados)
  - [Compara este enfoque con otros mecanismos de protección en sistemas operativos](#compara-este-enfoque-con-otros-mecanismos-de-protección-en-sistemas-operativos)
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
### Explica cómo esta matriz se utiliza para controlar el acceso en un sistema operativo.
### Simula un escenario donde un usuario intena acceder a un recurso no permitido y cómo la matriz lo bloquea.

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
### Diseña un esquema de validación para un sistema operativo con múltiples usuarios.

# Ejercicio 7: Cifrado
## Tareas:
### Define los conceptos de cifrado simétrico y asimétrico.
### Proporciona un ejemplo práctico de cada tipo de cifrado aplicado en sistemas operativos.
### Simula el proceso de cifrado y descifrado de un archivo con una clave dada.