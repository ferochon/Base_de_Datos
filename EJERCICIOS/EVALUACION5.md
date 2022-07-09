## Práctica 9.
### Operaciones en una base de datos.
Objetivo: Demostrar las operaciones que se realizan en una base de datos, aplicar el modelo relacional y el lenguaje SQL

Evaluación: Para poder tener correcto cada ejercicio deberán de mostrar el resultado que se da en cada respuesta.

Lista el nombre de todos los productos que hay en la tabla producto.


1. Lista los nombres y los precios de todos los productos de la tabla producto.

SELECT nom_prod, precio
FROM producto;

2. Lista todas las columnas de la tabla producto.


SELECT *
FROM fabricante
INNER JOIN fab_prod ON fabricante.id_fab=fab_prod.id_fab1
INNER JOIN producto ON fab_prod.cod_prod1= producto.cod_prod;



3. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de
todos los productos de la base de datos.

SELECT nombre_fab, nom_prod, precio
FROM fabricante
INNER JOIN fab_prod ON fabricante.id_fab=fab_prod.id_fab1
INNER JOIN producto ON fab_prod.cod_prod1= producto.cod_prod;


Subconsultas (En la cláusula WHERE)
1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER
JOIN).


2. Devuelve todos los datos de los productos que tienen el mismo precio que el
producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).


3. Lista el nombre del producto más caro del fabricante Lenovo.


https://www.db-fiddle.com/f/nLhAtXogcU7B5t72CdRe3E/4
