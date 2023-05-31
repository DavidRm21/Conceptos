

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

