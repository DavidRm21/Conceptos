# **Conexión a base de datos Java - MySql**
---

1. Tener instalado [MySQL](https://dev.mysql.com/downloads/installer/) o [XAMPP](https://www.apachefriends.org/download.html) en el sistema, y tener una base de datos creada.

2. Asegurarse de que se tiene el controlador JDBC de MYSQL.

    Puede descargarse en [MVN REPOSITORY](https://mvnrepository.com/artifact/mysql/mysql-connector-java) o en [MySQL](https://dev.mysql.com/downloads/connector/j/)

3. Agregar el JDBC a tu proyecto Java. Puede hacerse copiando el archivo .jar en el archivo de bibliotecas (libraries) de tu proyecto o configurando el controlador como una dependencia del sistema de construcción (Maven o Gradle).

4. Importar las clases necesarias en tu archivo Java, reemplazar el user, password, NombreDeTuBaseDeDatos con los valores adecuados para la configuración.


    <pre>
    import java.sql.Connection;
    import java.sql.DriverManager;
    import java.sql.SQLException;

    public class Conexion {

        private Connection connection;
        private String user = "root";
        private String password = "";

        public Conexion() {
            try{

                Class.forName("com.mysql.cj.jdbc.Driver");

                connection = DriverManager.getConnection(
                        "jdbc:mysql://localhost:3306/NombreDeTuBaseDeDatos",
                        user,
                        password);

                System.out.println("Conexión exitosa.");

            }catch (SQLException e){
                System.err.println("[ERROR] " + e);
            }
        }

        public  Connection getConnection(){
            return connection;
        }
    }
    </pre>

<br>

Luego de establecer la conexión podremos hacer uso de los siguientes objetos: 

- **Statement**: Se utiliza para enviar instrucciones SQL a una base de datos y ejecutar consultas. Puede ejecutar consultas SQL como SELECT, INSERT, UPDATE o DELETE. Sin embargo, ten en cuenta que los Statement no admiten parámetros, por lo que es necesario concatenar valores directamente en la cadena de consulta SQL, lo cual puede ser propenso a problemas de seguridad como la inyección de SQL.

- **PreparedStatement**: Se utiliza para enviar instrucciones SQL a una base de datos y ejecutar consultas, pero ofrece mejoras sobre los Statement en términos de rendimiento y seguridad.

- **ResultSet**: Representa el conjunto de resultados de una consulta SQL. Un ResultSet te *permite recorrer y acceder a los registros y los datos devueltos por la consulta.* Puedes moverte por el conjunto de resultados utilizando métodos como next(), que desplaza el cursor al siguiente registro, y acceder a los valores de las columnas utilizando métodos como getString(), getInt(), etc. 

    Un ResultSet también te permite realizar actualizaciones en la base de datos a través de los métodos updateRow(), insertRow(), deleteRow(), entre otros.

<br>
<br>

<details>
  <summary>Insertar datos (ejemplo)</summary>

  <pre>
  public void insertNewClient(int id, String name, String lastName, String email, String password, String phone){

        String query = "INSERT INTO cliente (cliente_id, nombre, apellido, correo, contrasena, telefono) " +
                "VALUES (?, ?, ?, ?, ?, ?)";

        try{
            conexion = connect.getConnection();
            preparedStatement = conexion.prepareStatement(query);
            preparedStatement.setInt(1, id);
            preparedStatement.setString(2, name);
            preparedStatement.setString(3, lastName);
            preparedStatement.setString(4, email);
            preparedStatement.setString(5, password);
            preparedStatement.setString(6, phone);

            preparedStatement.executeUpdate();

            JOptionPane.showMessageDialog(null, "Registro exitoso");

        }catch (SQLException e){
            System.out.println("[ERROR] " + e);
        }
    }
  </pre>

</details>

<br>

<details>
  <summary>Obtener registros de una consulta (ejemplo)</summary>

  <pre>
  public Room getRoomById(int id){
        String query = "SELECT habitacion_id, tipo, precio, capacidad, estado FROM habitacion WHERE habitacion_id = " + id;

        Room room = null;
        int h_id = 0;
        String type;
        float price;
        int capability;
        boolean state;

        try{
            conexion = connect.getConnection();
            statement = conexion.createStatement();
            resultSet = statement.executeQuery(query);

            while(resultSet.next()) {
                h_id = resultSet.getInt(1);
                type = resultSet.getString(2);
                price = resultSet.getFloat(3);
                capability = resultSet.getInt(4);
                state = resultSet.getBoolean(5);

                room = new Room(
                        h_id,
                        type,
                        price,
                        capability,
                        state     );
            }
        }catch (Exception e){
            System.out.println("[ERROR] "+ e);
        }
        return room;
    }
  </pre>

</details>

