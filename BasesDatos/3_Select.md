

<details>
  <summary><b>Base de datos implementada</b></summary>

-- Crear la base de datos "restaurant"
CREATE SCHEMA restaurant;

-- Indicar la base de datos que usaremos
USE restaurant;

-- Crear la tabla "Platos"
CREATE TABLE Platos (
    ID INT PRIMARY KEY,
    Nombre VARCHAR(50),
    Descripcion VARCHAR(100),
    Precio DECIMAL(10, 2)
);

-- Insertar filas en la tabla "Platos"
INSERT INTO Platos (ID, Nombre, Descripcion, Precio) VALUES
(1, 'Hamburguesa', 'Deliciosa hamburguesa con carne jugosa', 9.99),
(2, 'Pasta Alfredo', 'Pasta con salsa Alfredo y pollo', 12.99),
(3, 'Ensalada César', 'Ensalada fresca con pollo a la parrilla', 8.99);

-- Crear la tabla "Ordenes"
CREATE TABLE Ordenes (
    ID INT PRIMARY KEY,
    Fecha DATE,
    PlatoID INT,
    FOREIGN KEY (PlatoID) REFERENCES Platos(ID)
);

-- Insertar filas en la tabla "Ordenes"
INSERT INTO Ordenes (ID, Fecha, PlatoID) VALUES
(1, '2023-05-29', 1),
(2, '2023-05-29', 2),
(3, '2023-05-28', 3);

-- Agregar filas adicionales a la tabla "Platos"
INSERT INTO Platos (ID, Nombre, Descripcion, Precio) VALUES
(4, 'Pizza Margarita', 'Pizza clásica con salsa de tomate y queso mozzarella', 10.99),
(5, 'Sushi Variado', 'Selección de sushi fresco y variado', 14.99),
(6, 'Filete de Ternera', 'Filete jugoso de ternera con guarnición', 18.99),
(7, 'Pasta Primavera', 'Pasta con verduras frescas y salsa ligera', 9.99),
(8, 'Tarta de Manzana', 'Tarta casera de manzana con helado de vainilla', 6.99);

-- Agregar filas adicionales a la tabla "Ordenes"
INSERT INTO Ordenes (ID, Fecha, PlatoID) VALUES
(4, '2023-05-30', 4),
(5, '2023-05-30', 5),
(6, '2023-05-29', 6),
(7, '2023-05-29', 7),
(8, '2023-05-28', 8);

</details>

![Base de datos de ejemplo](./img/tablasEjemplo.jpg.)


<br>
<br>

## **Consultando una única tabla**
---

🆕 ***Trae todas las columnas de la tabla platos***

<pre>
SELECT * 
FROM Platos ;
</pre>

🆕 ***Trae las columnas nombre y precio de la tabla platos***

<pre>
SELECT nombre, precio 
FROM Platos ;
</pre>

🆕 ***Trae las columnas nombre y precio de la tabla platos y las organiza por nombres de manera ascendente***

<pre>
SELECT nombre, precio
FROM Platos
ORDER BY nombre ASC ;
</pre>

🆕 ***Trae las columnas nombre y precio de la tabla platos y las organiza por nombres de manera descendente***

<pre>
SELECT nombre, precio
FROM Platos
ORDER BY nombre DESC ;
</pre>

<br>

## **Colocando "Alias"**
---

🆕 ***Colocar alias a una columna***

<pre>
SELECT nombre AS nombre_plato
FROM Platos ;
</pre>

🆕 ***Colocar alias a una tabla***

<pre>
SELECT pl.nombre 
FROM Platos AS pl ;
</pre>

<br>

## **Filtrando la salida**
---

🆕 ***Trae todas las filas de la tabla platos donde el precio sea mayor a 9***

<pre>
SELECT * 
FROM platos
WHERE Precio > 9 ;
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el nombre NO contenga hamburguesa NI pasta Alfredo***

<pre>
SELECT * 
FROM platos 
WHERE Nombre != "Hamburguesa"
AND Nombre != "Pasta Alfredo"; 
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el nombre comience en P***

<pre>
SELECT * 
FROM platos 
WHERE nombre 
LIKE "p%" ;
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el nombre finalice en A***

<pre>
SELECT * 
FROM platos 
WHERE nombre 
LIKE "%a" ;
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el precio este entre el 8 y el 15***

<pre>
SELECT * 
FROM platos 
WHERE Precio 
BETWEEN 8 
AND 15 ;
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el precio NO sea nulo***

<pre>
SELECT * 
FROM platos 
WHERE Precio 
IS NOT NULL ;
</pre>

🆕 ***Trae todas las filas de la tabla platos donde el el ID sea 1, 3, 4, 8***

<pre>
SELECT * 
FROM platos 
WHERE ID 
IN (1,3, 4, 8) ;
</pre>

<br>
<br>

## **Consultando una varias tablas**
---

#### *JOIN o INNER JOIN*

###### Esta es la forma más común de realizar una unión y se utiliza para combinar registros relacionados en ambas tablas.

🆕 ***Trae la fila "nombre" de la tabla "platos" y la fila "fecha" de la tabla "ordenes" relacionados por la llave foranea en este caso el "ID"***

<pre>
SELECT platos.Nombre, ordenes.Fecha 
FROM platos 
INNER JOIN ordenes 
ON platos.ID = ordenes.ID ;
</pre>

#### *LEFT JOIN*

###### Devuelve todos los registros de la tabla de la izquierda y los registros coincidentes de la tabla de la derecha.

🆕 ***Trae la fila "nombre" de la tabla "platos" y la fila "fecha" de la tabla "ordenes" relacionados por la llave foranea en este caso el "ID" si no hay coincidencias de la tabla "platos", aparecera con valor NULL***

<pre>
SELECT platos.Nombre, ordenes.Fecha 
FROM platos 
LEFT JOIN ordenes 
ON platos.ID = ordenes.id ;
</pre>

#### *RIGTH JOIN*

###### Devuelve todos los registros de la tabla de la derecha y los registros coincidentes de la tabla de la izquierda.

🆕 ***Trae la fila "nombre" de la tabla "platos" y la fila "fecha" de la tabla "ordenes" relacionados por la llave foranea en este caso el "ID" si no hay coincidencias de la tabla "ordenes", aparecera con valor NULL***

<pre>
SELECT platos.Nombre, ordenes.Fecha 
FROM platos 
RIGTH JOIN ordenes 
ON platos.ID = ordenes.id ;
</pre>

#### *FULL JOIN o FULL OUTER JOIN*

###### Es útil cuando se desea combinar todas las filas de ambas tablas y analizar las diferencias entre ellas.

🆕 ***Trae todas las filas relacionadas y no relacionas por la llave foranea, donde no se relacione por defecto aparecerá NULL***

<pre>
SELECT * 
FROM platos 
FULL JOIN ordenes;
</pre>

