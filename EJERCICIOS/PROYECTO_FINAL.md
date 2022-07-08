# Proyecto Final de base de datos.
### Indicaciones de lo que se debe realizar

● Diseña el modelo entidad-relación del siguiente problema.

● Crea el script para la base de datos.
Proveedores

Tenemos que diseñar una base de datos sobre proveedores y disponemos de
la siguiente información:

● De cada proveedor conocemos su nombre, dirección, ciudad, provincia y
un código de proveedor que será único para cada uno de ellos.

● Nos interesa llevar un control de las piezas que nos suministra cada
proveedor. Es importante conocer la cantidad de las diferentes piezas
que nos suministra y en qué fecha lo hace. Tenga en cuenta que un
mismo proveedor nos puede suministrar una pieza con el mismo código
en diferentes fechas. El diseño de la base de datos debe permitir
almacenar un histórico con todas las fechas y las cantidades que nos ha
proporcionado un proveedor.

● Una misma pieza puede ser suministrada por diferentes proveedores.

● De cada pieza conocemos un código que será único, nombre, color,
precio y categoría.

● Pueden existir varias categorías y para cada categoría hay un nombre y
un código de categoría único.

● Una pieza sólo puede pertenecer a una categoría.

![image](https://user-images.githubusercontent.com/101203503/178055787-e6cd86fb-583b-4871-8757-0d64f0cd84e9.png)

https://www.db-fiddle.com/f/aoF6hnHYorCB3cUsQHRv1g/0

CREATE DATABASE proveedores_piezas;
USE proveedores_piezas;

CREATE TABLE prveedor(
cod_prov INT UNSIGNED PRIMARY KEY,
nom_prov VARCHAR(20),
dir_prov VARCHAR(100),
ciudad VARCHAR(20),
provincia VARCHAR(20)
);

CREATE TABLE pieza(
cod_pieza INT UNSIGNED PRIMARY KEY,
nom_pieza VARCHAR(20),
precio FLOAT UNSIGNED,
color VARCHAR(20)
);

CREATE TABLE nota(
cantidad_prov INT,
fecha DATE,
cod_prov1 INT UNSIGNED,
FOREIGN KEY (cod_prov1) REFERENCES prveedor(cod_prov),
cod_pieza1 INT UNSIGNED,
FOREIGN KEY (cod_pieza1) REFERENCES pieza(cod_pieza)
);

CREATE TABLE categoria(
cod_cat INT UNSIGNED,
nom_cat VARCHAR(20),
cod_pieza1 INT UNSIGNED,
FOREIGN KEY (cod_pieza1) REFERENCES pieza(cod_pieza)
);


