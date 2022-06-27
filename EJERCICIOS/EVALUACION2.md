## Práctica 3.
### Introducción a SQL
Objetivo: Demostrar la correcta identificación de los conceptos del lenguaje SQL
Ejercicio:

1. Menciona los comandos DMl: (valor .85)

SELECT, UPDATE, DELETE, INSERT


2. Menciona 3 tipos de datos que existen: (valor .85)
INT
CHAR
DATE



3. ¿Qué diferencia existe entre TRUNCATE y DELETE?(valor .85)
Truncate 
TRUNCATE es una operación DDL que borra todo el coentenido de una tabla miemtras DELETE es una operación DML que permite el borrado selectivo de filas de una tabla

4. ¿Para qué se utiliza el atributo UNIQUE?(valor .85)

     Es una caraceristica que se agrega a un campo para especificar que tienen datos que no se repetiten en ninguna tabla

5. ¿Qué diferencia hay entre los tipos de datos VARCHAR y CHAR? (valor .85)

En los datos de tipo char se reserva un espacio de memoria mientras que en VARCHAR el espacio se ajusta al tamaño del dato
introdicido sin necesariamente ocupar la totalidad de espacio reservado si no se ocupó.

6. Defina brevemente el significado de las siglas SQL(valor .85)
Structured Query Language lenguaje de consulta estructurado que permite realizar consultas y recuperar información de una
manera sencilla por medio de calculos relacionales y algebrícos.

7. Defina brevemente qué es MySQL WorkBench (valor .85)
 Es una herramineta con interfce visual que peremite la construcción de diagramas de bases de datos relacionales.

## Práctica 5.
### Gestores de base de datos

Objetivo: Categorizar los distintos gestores de base de datos que existen y señalar las
ventajas y desventajas

Evaluación: Conoce los tipos de gestores de base de datos 3 puntos.
MySQL, MariaDB, SQLite

Domina sus diferencias de los gestores de base de datos mencionados 3 puntos
Establecen vínculos o relaciones entre datos
Sirven como interface entre las bases de datos, los usuarios y las aplicaciones
Permite realizar consultas
MySQL proyecto de código abierto de ORACLE
SQLITE disponible al público
MariaDB soporta muchos motores de almcenamiento

Ejercicio:

En un mapa conceptual presenta 3 gestores de bases de datos, sus características
principales, las ventajas y desventajas. (valor 6)

![image](https://user-images.githubusercontent.com/91554777/170415427-e2b7321b-a97f-43b0-ac24-6e506c307e6b.png)


GESTORES DE BASES DE DATOS
MySQL	MariaDB	SQLite
Característica	Característica	Característica
Gratuito
Multiplataforma
Interfaz gráfica
Sistema de respaldo de datos
Sistema de mantto. y reparación
Acceso simultaneo a varios empleados
Privilegios de seguridad
Función de replicación de la BD	Es básicamente un fork de MySQL, cada vez que sale una nueva versión de MySQL sale una de MariaDB, su propósito es mantener una base de datos libre
	Versión de SQL reducida para aplicaciones pequeñas que requieren bases de datos.
Multisistema
Código abierto
Soporta múltiples tablas
No necesita configuración
Autonomía

Ventajas	Ventajas	Ventajas
MySQL es además un software fácil de instalar y también fácil de configurar.
Otra de sus ventajas principales es el rendimiento, sobre todo si ejecutamos consultas sencillas.
Tiende a ser extremadamente estable	Nuevos motores de almacenamiento más eficientes que la hacen más rápida.
Añadidura de estadísticas para índices y tablas que ayudan a la optimización de la base de datos.
En general mejoras para aumentar el rendimiento y la eficiencia con respecto a MySQL
	Fácil de usar
Ideal para desarrollo de apps móviles
Las consultas se realizan en SQL lo que reduce la complejidad del código de la app
Ocupa poco espacio

Desventajas	Desventajas	Desventajas
En sistemas con mucho tráfico esto puede volverse un gran problema	La migración de MySQL a MariaDB es compleja.
	No es fácilmente escalable
No cuenta con funciones de seguridad ni permisos de administración de usuario lo que puede hacerlo inseguro
Es monousuario
No ideal para bases de datos de gran tamaño (restringido a 2 GB)




## Práctica 6.
### Herramienta en línea y ejercicio necesarios para realizar las prácticas

Creación de base de datos.

Objetivo: Demostrar mediante la creación de una base de datos el uso y la aplicación de
las funciones

Ejercicio: Creación de la base de datos (valor 18 puntos)

Tienda de informática

![image](https://user-images.githubusercontent.com/91554777/170415101-717bca19-3644-46a9-8a57-8d5940c5d283.png)




Modelo entidad/relación

![image](https://user-images.githubusercontent.com/101203503/175651027-db420c8a-de9a-407b-aee4-27ff4b50c5cb.png)



Base de datos para MySQL


CREATE DATABASE Fabricantes;
USE Fabricantes;

CREATE TABLE fabricante(
id_fab VARCHAR(100) PRIMARY KEY,
nombre_fab VARCHAR(100)  
);

INSERT INTO fabricante VALUES('C1','SEAGATE'); 
INSERT INTO fabricante VALUES('C2','CRUCIAL');
INSERT INTO fabricante VALUES('C3','SAMSUNG');
INSERT INTO fabricante VALUES('C4','GIGABYTE');
INSERT INTO fabricante VALUES('C5','ASUS');
INSERT INTO fabricante VALUES('C6','LENOVO');


CREATE TABLE producto(
cod_prod VARCHAR(100) PRIMARY KEY,
nom_prod VARCHAR(100),  
precio float 
);

INSERT INTO producto VALUES('DB-23','DISCO DURO SATA3 1TB', 86.99);
INSERT INTO producto VALUES('MM-34','MEMORIA RAM DDR4 8GB', 120.6);
INSERT INTO producto VALUES('DD-98','DISCO SSD 1TB', 150.99);
INSERT INTO producto VALUES('MM-98','GeFORCE GTX 1050Ti', 185.7);
INSERT INTO producto VALUES('MM-23','GeFORCE 1080 Xtreme', 755.6 );
INSERT INTO producto VALUES('MT-12','MONITOR 24 led Full HD', 202.1);
INSERT INTO producto VALUES('MT-08','MONITOR 27 led Full HD', 245.99);
INSERT INTO producto VALUES('LP-19','PORTATIL YOGA 520', 559.2);
INSERT INTO producto VALUES('LP-11','PORTATIL Ideapd 320', 444.2);
INSERT INTO producto VALUES('IM-56','Impresora HP DEskyet 3720', 59.99);
INSERT INTO producto VALUES('LP-54','Impresora HP Laserjet Pro M26nw', 180.3);

CREATE TABLE fab_prod(
folio VARCHAR(20),
cantidad float,
fecha DATE,
id_fab1 VARCHAR(50),
FOREIGN KEY (id_fab1) REFERENCES fabricante(id_fab),  
cod_prod1 VARCHAR(10),  
FOREIGN KEY (cod_prod1) REFERENCES producto(cod_prod)  
);




