En la BD utilizada en clase realiza las siguientes consultas:

* La tabla empleado
 
SELECT nombre_periodista, apellidos_periodista, especialidad
FROM periodistas;

* Los titulos de las revistas

SELECT titulo
FROM revista;
 
* Los nombres, apellidos y especialidad de los periodostas
 
SELECT nombre_periodista, apellidos_periodista, especialidad
FROM periodistas;

* Muestra los empleados que estan en x sucursal

SELECT nombre_empleado, codigo_de_sucursal
FROM empleados INNER JOIN sucursal ON sucursal.codigo_de_sucursal=empleados.codigo_de_sucursal1
WHERE nombre_empleado = 'Angelica';

* Muestra que periodistas colaboraron en x revista y en que sucursal se publico la revista

SELECT nombre_periodista, apellidos_periodista, titulo, codigo_de_sucursal
FROM periodistas INNER JOIN trabajan ON periodistas.nif=trabajan.nif1
INNER JOIN revista ON trabajan.numero_de_registro2=revista.numero_de_registro
INNER JOIN publican ON revista.numero_de_registro=publican.numero_de_registro1
INNER JOIN sucursal ON publican.codigo_de_sucursal2=sucursal.codigo_de_sucursal
WHERE nombre_periodista='TITO';

* Mustra que seccion esta en x revista, en que sucursal se imprimio y que empleados estan en esa sucursal.

SELECT titulo_secciones, titulo_revista, codigo_de_sucursal, nombre_empleado, apellidos_empleado
FROM  secciones
INNER JOIN revista ON secciones.numero_de_registro3= revista.numero_de_registro
INNER JOIN publican ON revista.numero_de_registro= publican.numero_de_registro1
INNER JOIN sucursal ON publican.codigo_de_sucursal2 =sucursal.codigo_de_sucursal 
INNER JOIN empleados ON sucursal.codigo_de_sucursal=empleados.codigo_de_sucursal1

* En la tabla peridistas muestra solo los que escriban sobre cine

SELECT nombre_periodista, apellidos_periodista, especialidad
FROM periodistas
WHERE especialidad='CINE';

* De la tabla revistas muestra las que sean de publicacion quincenal

SELECT titulo_revista, periodicidad
FROM revista
WHERE periodicidad='QUINCENAL';

* Muestra el nombre de ka revista que se hayan impreso despues del 30 de septiembre del 2021

SELECT titulo_revista,fecha
FROM revista
INNER JOIN ejemplares ON revista.numero_de_registro=ejemplares.numero_de_registro4
WHERE fecha >'2021-09-30';

* Muestra el nombre de la revista que se haya publicado en la sucursal 1 cuyos ejemplares tengan más de 80 páginas.

SELECT titulo_revista, codigo_de_sucursal, ID, numero_de_paginas
FROM sucursal
INNER JOIN publican ON sucursal.codigo_de_sucursal=publican.codigo_de_sucursal2
INNER JOIN revista ON publican.numero_de_registro1=revista.numero_de_registro
INNER JOIN ejemplares ON revista.numero_de_registro=ejemplares.numero_de_registro4
WHERE  codigo_de_sucursal=01 && numero_de_paginas > 80;


https://www.db-fiddle.com/f/iAUjGLoFoHtam2pK68Xh1B/1

