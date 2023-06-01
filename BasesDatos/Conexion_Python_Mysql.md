# **Conexión a base de datos Python - MySql**
---

1. Tener instalado [MySQL](https://dev.mysql.com/downloads/installer/) o [XAMPP](https://www.apachefriends.org/download.html) en el sistema, y tener una base de datos creada.

2. Instalar el paquete mysql-connector-python en el entorno de Python. Puede hacerse mediante el administrador de paquetes "pip" ejecuntandolo en la consola:

    > pip install mysql-connector-python
    
    <details>
    <summary>Utilizar pip</summary>
    - Para verificar si tienes instalado pip, escribe en tu consola

    <pre> pip --version </pre>

    Si aparece un error puedes instalarlo [Aquí](https://bootstrap.pypa.io/get-pip.py), es necesario que este añadido en las variables de entorno para poder usar el comando en la consola de Windows.

    </details>

    Luego de haber guardado el paquete lo instalamos con el comando:

    > python get-pip.py
 
3. Importar el modulo mysql-connector en el archivo .py

    <pre>import mysql.connector</pre>

4. Establecer la conexión con la base de datos utilizando la configuración adecuada:

    <pre>
    def conexion():
        myConection = mysql.connector.connect(
        host="localhost",
        user="tu_usuario",
        password="tu_contraseña",
        database="nombre_basedatos"
        )
        return myConection
    </pre>

5. Luego de establecer la conexión podremos crear el objeto cursor para interactuar con la base de datos

- ***Insertar datos***
    <pre>
    def insert(valor1, valor2):
        myConection = conexion()
        myCursor = myConection.cursor()

        myCursor.execute(f'INSERT INTO nombreDeLaTabla (columna1, columna2) VALUES ("{valor1}", {valor2})')
        
        myConection.commit()
        myConection.close()
    </pre>

- ***Leer datos***
    <pre>
    def read():
        myConection = conexion()
        myCursor = myConection.cursor()

        myCursor.execute('SELECT * FROM nombreDeLaTabla')

        result = cursor.fetchall()

        for fila in result:
            print(fila)
        
        cursor.close()
        myConection.close()
    </pre>
