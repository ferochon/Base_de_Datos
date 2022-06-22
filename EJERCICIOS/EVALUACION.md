## Práctica 1.

1. Introducción a base de datos

Objetivo: Identificar el nivel de comprensión de los conceptos de base de datos,
mediante preguntas abiertas.
 
Preguntas:

1. ¿Cuáles son las cinco funciones principales del administrador de bases de datos?
(valor 1.5)

Asegurar el buen funcionamiento de las Base  de datos
Retención de la información 
Evitar pérdida de datos
Solucionar incidencias
Garantizar la seguridad de los datos

2. Indíque cinco responsabilidades del sistema gestor de bases de datos (valor 1.5)

Instalar, configurar y gestionar bases de datos.
El soporte al equipo de desarrollo, seguridad informática y redes.
Define el esquema del diccionario de datos.
Especificar restricciones de integridad para asegurar los datos.
Garantizar la alta disponibilidad de la base de datos.

3. En una BD al usuario del sistema se le brindarán recursos para realizar diversas
operaciones sobre estos archivos, tales como: (valor 1.5)


Almacenar datos de forma estructurada y acceder a ellos cuando lo requiera, le ayuda a crear sus propias bases de datos
Supervisión del rendimiento de la base desatos, ajuste, copias de seguiridad y recupeación de información.

4. ¿Qué es un Sistema de Información? (valor 1.5)

Es unconjunto organizado de lementos destinados para el tratamiento y administración de datos, organizados y listos para su posterior uso, generados para cubrir necesidades específicas

## Práctica 2.

2. Diseño de un modelo relacional

Objetivo: Representar desde un modelo entidad relación un problema


Ejercicio:

Tenemos que diseñar una base de datos sobre proveedores y disponemos de la siguiente
información:

Realiza el modelo entidad relación. (valor 6)

Tenemos esta información sobre una cadena editorial:

● La editorial tiene varias sucursales, con su domicilio, teléfono y un código de
sucursal.

● Cada sucursal tiene varios empleados, de los cuales tendremos su nombre,
apellidos, NIF y teléfono. Un empleado trabaja en una única sucursal.

● En cada sucursal se publican varias revistas, de las que almacenaremos su título,
número de registro, periodicidad y tipo.

● Una revista puede ser publicada por varias sucursales.

● La editorial tiene periodistas (que no trabajan en las sucursales) que pueden
escribir artículos para varias revistas. Almacenaremos los mismos datos que para
los empleados, añadiendo su especialidad.

● También es necesario guardar las secciones fijas que tiene cada revista, que
constan de un título y una extensión.

● Para cada revista, almacenaremos información de cada ejemplar, que incluirá la
fecha, número de páginas y el número de ejemplares vendidos.


![image](https://user-images.githubusercontent.com/101203503/175119099-ec40bde8-1882-4107-acc0-4dc59a1a19b9.png)





