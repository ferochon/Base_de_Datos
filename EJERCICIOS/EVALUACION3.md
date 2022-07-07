
## Práctica 4
### Data warehouse

Objetivo: Demostrar la identificación de los elementos que componen data warehouse y
su esquema

Ejercicio:

1. ¿Qué es un DataWarehouse?(valor 2)

  Es un repositorio estructurado unificado para todos los datos que recogen los diversos sistemas (fuentes que nos avastecen de datos) de una empresa.

2. Realiza un diseño del modelo en estrella (valor 2)

    De hecho un red de computadoras puede ser un modelo en estrella dónde el servidor provee de recusrsos a un conjunto de "clientes"

![image](https://user-images.githubusercontent.com/101203503/177344476-eec03c68-30a8-4e3a-86f8-47cd7cb28c7a.png)

![image](https://user-images.githubusercontent.com/101203503/177885748-f5ec30f0-ef58-46af-b0cd-5fab858dbc4c.png)





3. Realiza un diseño del modelo copo de nieve (valor 2)


Se llama como de nieve porque su diagrama se asemeja a un copo de nieve.

![image](https://user-images.githubusercontent.com/101203503/177872302-1e38a6ce-8e73-4f32-8cd1-12606bf0e85c.png)



## Práctica 7
### Funciones en SQL
Objetivo: Demostrar el uso y aplicación en una base de datos para mejorar la gestión

Ejercicio:

1. Calcula el número total de productos que hay en la tabla productos. (valor 4.5)

USE Fabricantes;

SELECT COUNT(cod_prod)
FROM producto;

2. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado
también debe incluir los fabricantes que no tienen ningún producto. El resultado
mostrará dos columnas, una con el nombre del fabricante y otra con el número de
productos que tiene. Ordene el resultado descendentemente por el número de
productos. (valor 4.5)

SELECT nombre_fab, COUNT(cod_prod)
FROM fabricante
INNER JOIN fab_prod ON fabricante.id_fab=fab_prod.id_fab1
INNER JOIN producto ON fab_prod.cod_prod1=producto.cod_prod
GROUP BY(nombre_fab)
ORDER BY (nombre_fab) DESC;


3. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada
uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los
datos que se solicitan. (valor 4.5)

 USE Fabricantes;


SELECT nombre_fab, MAX(precio), MIN(precio), AVG(precio)
FROM fabricante
INNER JOIN fab_prod ON fabricante.id_fab=fab_prod.id_fab1
INNER JOIN producto ON fab_prod.cod_prod1=producto.cod_prod
GROUP BY(nombre_fab);


4. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo,
precio medio y el número total de productos de los fabricantes que tienen un precio
medio superior a 200€. Es necesario mostrar el nombre del fabricante. (valor 4.5)

https://www.db-fiddle.com/f/dboNhzkCAEpkTdoQiR6pQq/5

SELECT nombre_fab, MAX(precio), MIN(precio), AVG (precio), COUNT(cod_prod)
FROM fabricante
INNER JOIN fab_prod ON fabricante.id_fab=fab_prod.id_fab1
INNER JOIN producto ON fab_prod.cod_prod1=producto.cod_prod
GROUP BY (nombre_fab)
HAVING AVG(precio)>200;

