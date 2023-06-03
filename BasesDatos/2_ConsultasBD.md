# **¿Qué es SQL?**

SQL es un lenguaje de programación que permite interactuar con bases de datos relacionales para realizar consultas, manipulaciones y administración de datos. Es esencial en el campo de la gestión de bases de datos y es utilizado por profesionales en el desarrollo de software, análisis de datos y otras áreas relacionadas con la gestión de información.

En términos simples, SQL es el lenguaje que se utiliza para comunicarse con una base de datos. Permite realizar consultas para obtener información específica de una base de datos, insertar nuevos datos, actualizar registros existentes, eliminar registros y realizar diversas operaciones relacionadas con la gestión de datos.

<br>
<br>
<br>

# **SQL tiene contiene 4 sublenguajes**

<br>

## **DDL**
(Data Definition Language) se utiliza para definir y administrar la estructura y el esquema de una base de datos. 

Los comandos DDL más comunes son:

- **CREATE:** Se utiliza para crear objetos de la base de datos, como tablas, índices, vistas, funciones almacenadas y procedimientos almacenados.

- **ALTER** Permite modificar la estructura de los objetos de la base de datos existentes, como añadir o eliminar columnas de una tabla, modificar el tipo de datos de una columna o cambiar el nombre de un objeto.
- **DROP** Se utiliza para eliminar permanentemente objetos de la base de datos, como tablas, vistas, índices, funciones almacenadas, entre otros.
- **TRUNCATE** Permite eliminar todos los datos de una tabla, manteniendo la estructura de la tabla intacta.
- **RENAME** Permite cambiar el nombre de un objeto de la base de datos, como una tabla o una columna.
- **CONSTRAINT** Se utiliza para definir restricciones en las tablas, como claves primarias, claves foráneas, restricciones de integridad, entre otros.


<br>
<br>

## **DML**
(Data Manipulation Language) se utiliza para manipular y operar sobre los datos almacenados en una base de datos. 

Los comandos DML más comunes son:

- **SELECT**: Se utiliza para recuperar datos de una o varias tablas en la base de datos.

- **INSERT**: Permite insertar nuevos registros en una tabla de la base de datos. 

- **UPDATE**: Se utiliza para modificar los datos existentes en una o varias filas de una tabla. 

- **DELETE**: Permite eliminar uno o varios registros de una tabla en la base de datos. 

<br>
<br>

## **DCL**
(Data Control Language) se utiliza para controlar los permisos de acceso y la seguridad en una base de datos.

- **GRANT**: Se utiliza para otorgar privilegios y permisos de acceso a los usuarios sobre los objetos de la base de datos. *Leer, escribir, modificar o eliminar* datos en tablas.

- **REVOKE**: Permite revocar o retirar los privilegios y permisos otorgados previamente a los usuarios.

- **DENY**: Permite negar explícitamente ciertos privilegios a los usuarios.

<br>
<br>

## **TCL**
(Transaction Control Language) Son utilizados para gestionar y controlar transacciones en una base de datos. 

Los comandos más comunes son:

- **COMMIT**: Se utiliza para confirmar una transacción y aplicar permanentemente los cambios realizados en la base de datos.

- **ROLLBACK**: Permite deshacer una transacción en su totalidad, descartando todos los cambios realizados.

- **SAVEPOINT**: Se utiliza para establecer puntos de control dentro de una transacción, lo que permite deshacer solo una parte de la transacción hasta un punto específico. 

<br>
<br>

# **Consultas SQL**

---

<details>
  <summary><b> ✔️ Recomendaciones antes de empezar con las consultas</b></summary>

1. Utiliza nombres que sean claros y concisos para facilitar la comprensión.

2. Evitar caracteres especiales.

3. Decide si utilizarás nombres en singular o en plural para las tablas y mantenlo consistente en todo el esquema de la base de datos. 

4. Convenciones de formato (nombreTabla, NombreTable, Nombre_Tabla, nombre_tabla)

5. Evitar palabras reservadas.

</details>

---

<br>
<br>

## **Pasos para crear una base de datos**
---

#### 1. ***Con está sentencia creamos la base de datos***
<pre>
CREATE DATABASE nombreBaseDeDatos;
</pre>

#### 2. ***Le indicamos al lenguaje que base de datos vamos a modificar***

<pre>
USE nombreBaseDeDatos;
</pre>

#### 3. ***En este ejemplo crearemos dos tablas y una llave foránea***

<pre>
CREATE TABLE nombreDeLaTabla  (   
    id_tabla INT(50) PRIMARY KEY AUTO_INCREMENT,
    atributo1 VARCHAR(40) NOT NULL,
    atributo2 VARCHAR(60) DEFAULT 0,
    atributo3 VARCHAR(255) NOT NULL UNIQUE,
    atributo4 INT(50) CHECK (atributo4 >= 18)
);

CREATE TABLE nombreDeLaTabla2  (   
    id_tabla2 INT(50) PRIMARY KEY,
    atributo1 VARCHAR(40) NOT NULL,
    atributo2 VARCHAR(60) DEFAULT 'Desconocido',
    atributo3 VARCHAR(255) NOT NULL UNIQUE,
    atributo4 VARCHAR(30),
    FKatributo INT(50) NOT NULL,
    FOREIGN KEY (FKatributo) REFERENCES nombreDeLaTabla(id_tabla)
);  
</pre>

<br>

🆕 ***Añade una llave foranea a una columna en una tabla existente.***

<pre>
ALTER TABLE nombreDeLaTabla
ADD FOREIGN KEY (nombreColumnaActual) 
REFERENCES nombreDeLaTabla2(PRIMARY KEY) 
ON UPDATE CASCADE ON DELETE NO ACTION; 
</pre>

***

🆕 ***Añadir una columna adicional en una tabla.*** 

<pre>
ALTER TABLE nombreDeLaTabla
ADD nombreDeLaColumna tipoDato;
</pre> 

###### [ 🔎tipos de datos](img/tiposDatos.jpg)

***

🔁 ***Alterar una columna y cambiar sus propiedades(tipo, capacidad, reglas, etc.)***

<pre>
ALTER TABLE nombreDeLaTabla
ALTER COLUMN nombreDeLaColumna VARCHAR(25); 
</pre>

***

🔁 ***Renombrar una columna en una tabla.***

<pre>
ALTER TABLE nombreDeLaTabla
RENAME COLUMN nombreDeLaColumna TO nuevoNombre; 
</pre>

***

🔁 ***Renombrar una tabla existente***

<pre>
ALTER TABLE nombreDeLaTabla
RENAME TABLE nombreDeLaTabla TO nuevoNombre; 
</pre>

***

### 💾 ***Guardará la base de datos en un terminal o dispositivo de almacenamiento.*** 

<pre>
BACKUP DATABASE nombreBaseDeDatos
TO DISK = 'filepath';
</pre>



<br>
<br>



***

🔥⛔️ ***Elimina el contenido de la tabla pero no la tabla***

<pre>
TRUNCATE TABLE nombreDeLaTabla;
</pre>

***

🔥 ***Eliminar una columna de una tabla.***

<pre>
ALTER TABLE nombreDeLaTabla
DROP COLUMN nombreDeLaColumna;
</pre>

> ### - ❗️👀 ⛔️***Eliminará permanentemente la base de datos***❗️
> <pre>DROP DATABASE nombreBaseDeDatos;</pre>
> ### - ⛔️ Esta nos eliminará permanentemente la tabla definida
> <pre>DROP TABLE nombreDeLaTabla;</pre>

<br>
<br>
<br>

## **Manipular los registros de la base de datos**
---


🆕 ***Insertar datos en una tabla***

<pre>
INSERT INTO nombreDeLaTabla (nombreDeLaColumna1, nombreDeLaColumna2, ...)
VALUES (valorColumna1, valorColumna2, ...);
</pre>

🔁 ***Actualizar datos en una tabla***

<pre>
UPDATE nombreDeLaTabla 
SET nombreDeLaColumna1 = valorColumna1 
WHERE condicion;
</pre>

🔥 ***Eliminar filas de una tabla***

<pre>
DELETE FROM nombreDeLaTabla 
WHERE condicion;
</pre>

🔎 [***Permite seleccionar columnas específicas de una tabla, filtrar registros con condiciones, realizar cálculos y agregaciones, ordenar los resultados, etc.***](3_Select.md)

<pre>
SELECT nombreDeLaColumna FROM nombreDeLaTabla;
</pre>




