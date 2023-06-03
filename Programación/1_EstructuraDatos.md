# **Estructura de datos**

---
Una estructura de datos es una forma de organizar y almacenar nuestros datos para que podamos trabajar con ellos de manera más eficiente. Nos ayuda a mantener los datos ordenados y a realizar operaciones sobre ellos de manera rápida y sencilla.

Una estructura de datos puede ser pensada como un organizador o contenedor especial donde podemos poner diferentes tipos de datos, como números, palabras o cualquier otra información que necesitemos almacenar. Esta estructura nos permite realizar acciones sobre los datos, como buscar, agregar o eliminar elementos de forma rápida y eficiente.

<br>
<br>


### ***Ventajas:***

- **Eficiencia en el acceso y procesamiento de datos:** Las estructuras de datos están diseñadas para permitir un acceso rápido y eficiente a los datos, lo que mejora el rendimiento y la eficiencia del programa.

- **Optimización del uso de memoria:** Las estructuras de datos están diseñadas para utilizar eficientemente la memoria y reducir el desperdicio de espacio, permitiendo una gestión efectiva de los recursos.

- **Facilidad de manipulación de datos:** Las estructuras de datos proporcionan operaciones y algoritmos predefinidos para agregar, eliminar, buscar y manipular datos de manera conveniente y eficiente.


### ***Desventajas:***

- **Complejidad en la implementación:** Algunas estructuras de datos pueden requerir una implementación compleja y detallada, lo que puede aumentar la complejidad del código y la posibilidad de errores.

- **Limitaciones en el tamaño y capacidad**: Algunas estructuras de datos tienen un tamaño o capacidad máxima predefinida, lo que puede ser limitante si se necesita almacenar una gran cantidad de datos o si los requisitos de tamaño son variables.

<br>
<br>

![Que_son_las_estructuras_de_datos](./img/edjpg.jpg)

<br>
<br>

La ventaja de utilizar estructuras de datos es que nos permiten manejar grandes cantidades de información de manera más organizada y eficiente. Podemos acceder a los datos rápidamente y realizar operaciones sobre ellos de manera sencilla.

Sin embargo, también es importante tener en cuenta que cada estructura de datos tiene sus propias ventajas y desventajas. Algunas pueden ser más eficientes para buscar elementos rápidamente, mientras que otras pueden ser más útiles para agregar o eliminar elementos con facilidad.

<br>
<br>

## Podemos clasificar las estructuras en dos grandes grupos:

**Lineales:** Estas estructuras de datos organizan los elementos en una secuencia lineal, donde cada elemento tiene un sucesor y un predecesor, excepto el primero y el último elemento. 



<details>
<summary><b>🔍 Arreglos (Arrays)</b></summary>
Imagina que tienes una caja con varios compartimentos numerados. Cada compartimento puede contener un objeto. Ahora, piensa en esos compartimentos como un arreglo. Un arreglo es una estructura de datos que nos permite almacenar una colección de elementos del mismo tipo en una secuencia ordenada.

<br>

![Organizador_de_caja](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fhttp2.mlstatic.com%2Forganizador-de-64-gavetas-promocion-truper-10895-D_NQ_NP_842967-MLM31224146550_062019-F.jpg&f=1&nofb=1&ipt=842b7f3aeba45f171aadfb4e15a98251b59a0eb02b4c3845e8534e6086764056&ipo=images)

<br>

Cada elemento en el arreglo tiene una posición única, llamada índice, que comienza desde cero. Es como si cada compartimento en la caja tuviera un número, y podemos acceder a cada objeto específico utilizando ese número.

<br>

### **Ventaja**
- La ventaja de utilizar arreglos es que nos permiten almacenar varios elementos en un solo lugar y acceder a ellos de forma rápida y sencilla utilizando su índice.

### **Desventaja**
- Los arreglos tienen un tamaño fijo una vez que se crean, lo que significa que no pueden crecer o disminuir dinámicamente. Esto significa que debemos especificar el tamaño del arreglo al crearlo y no podemos agregar o eliminar elementos más allá de ese tamaño inicial.

---

### Usos
- Aplicaciones de procesamiento de imagen

- Sistema de gestión de bases de datos

- Aplicaciones de análisis financiero

- Simulaciones y juegos

- Aplicaciones científicas

- Aplicaciones de procesamiento de texto

</details>

<br>

<details>
 <summary><b>🔍 ArrayList</b></summary>

Imagina que tienes una lista de cosas y quieres guardarla en un papel. Si tienes más cosas para agregar a la lista, tendrás que agregarlas al final o entre los elementos existentes. Ahora, piensa en esa lista como un ArrayList.

<br>

![Lista_de_compras](https://imagens-revista.vivadecora.com.br/uploads/2018/04/Lista-de-compras-no-papel.jpg)

Un ArrayList es una estructura de datos en la programación que nos permite almacenar una colección de elementos en una secuencia ordenada y dinámica. A diferencia de un arreglo tradicional, un ArrayList puede crecer o disminuir de tamaño automáticamente según agreguemos o eliminemos elementos.

<br>

## **Ventaja**

- Nos brinda flexibilidad en términos de tamaño. No necesitamos especificar un tamaño fijo al crearlo, como en un arreglo. Podemos agregar elementos fácilmente utilizando el método add() y eliminar elementos utilizando el método remove(). El ArrayList se ajustará automáticamente para acomodar los cambios en la cantidad de elementos.

## **Desventajas**

- Mayor consumo de memoria debido a la capacidad interna que puede ser mayor que la cantidad de elementos reales. Además, las operaciones de inserción y eliminación en posiciones intermedias pueden ser menos eficientes en comparación con un arreglo tradicional. 

---

## Usos

- Aplicación de gestión de contactos

- Sistemas de inventario y ventas

- Aplicaciones de redes sociales

- Aplicación de reproducción de musica

- Registro de eventos

</details>

<br>

<details>
 <summary><b>🔍 Listas Enlazadas (Linked Lists)</b></summary>

Imagina una cadena de personas tomadas de la mano. Cada persona tiene un brazo libre que puede sostener la mano de otra persona. Ahora, piensa en esa cadena de personas como una lista enlazada.

<br>

![Personas_tomadas_de_la_mano](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fimage.freepik.com%2Ffoto-gratis%2Famigos-tomados-mano-al-atardecer_53876-10578.jpg&f=1&nofb=1&ipt=d430791cf2aaf87e5e0c437612e4e9d5096ec362c62eabfbb5009d9a582106c8&ipo=images)

<br>

Una lista enlazada es una estructura de datos en la que cada elemento, llamado nodo, contiene un valor y una referencia (o enlace) al siguiente nodo en la lista. A diferencia de un arreglo, los nodos de una lista enlazada no se almacenan de manera contigua en la memoria, sino que pueden estar dispersos en diferentes ubicaciones.

<br>

## **Ventaja**

- Permite una inserción y eliminación eficiente de elementos en cualquier posición de la lista. Cuando se inserta un nuevo nodo en la lista, se actualizan los enlaces de los nodos vecinos para incluir el nuevo nodo. Del mismo modo, cuando se elimina un nodo, los enlaces se ajustan para excluir el nodo eliminado.

## **Desventajas**

- El acceso a un nodo en una posición específica puede ser más lento en comparación con un arreglo. Para acceder a un nodo en una lista enlazada, se debe recorrer la lista desde el nodo inicial hasta el nodo deseado, siguiendo los enlaces entre los nodos.

---

## Usos

- Implementación de pilas y colas

- Manejo de memoria en sistemas operativos

- Editor de texto

- Historial de navegación de un ordenador

- Listas de reproducción de música


</details>

<br>

<details>
  <summary><b>🔍 Pilas (Stacks)</b></summary>

Imagina una pila de platos en un restaurante. Cada vez que se lava un nuevo plato, se coloca en la parte superior, y cuando se quiere tomar un plato, siempre se toma el que está en la parte superior de la pila.

<br>

![Pila_de_platos](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.FR-vZvNEe9nID8HZysvrMAHaKE%26pid%3DApi&f=1&ipt=fa5d1bca3fe720614cd1af5ecb94ba9d9c7ee55555886a472316208e0169702b&ipo=images)

<br>

Una pila es una estructura de datos en la que los elementos se agregan y eliminan siguiendo el principio LIFO (Last In, First Out). Es similar a una pila de platos, donde el último plato que se agrega es el primero en ser eliminado.

>Las operaciones principales que se realizan en una pila son:
>
> - "Push": Agregar un elemento a la parte superior de la pila.
> - "Pop": Eliminar y retornar el elemento en la parte superior de la pila.
> - "Peek" o "Top": Obtener el valor del elemento en la parte superior de la pila sin eliminarlo.

<br>

## **Ventaja**

- **Eficiencia en operaciones:** Las operaciones principales en una pila, como "push" (agregar un elemento) y "pop" (eliminar un elemento), se realizan en tiempo constante O(1). 

- **Estructura simple:** Las pilas son estructuras de datos simples y fáciles de entender. 

- **Gestión de memoria:** Las pilas son útiles para gestionar la memoria en la pila de ejecución de un programa. Cada vez que se llama a una función, se agrega un marco de pila para almacenar las variables locales y los datos relacionados. Cuando la función termina, el marco se elimina automáticamente, lo que ayuda a gestionar eficientemente la memoria y evitar fugas de memoria.

## **Desventajas**

- **Acceso limitado:** El acceso a los elementos en una pila está restringido solo al elemento en la parte superior. No es posible acceder o modificar elementos en posiciones intermedias o inferiores sin eliminar primero los elementos superiores de la pila.

- **Tamaño limitado:** Las pilas tienen un tamaño máximo fijo, que está determinado por el espacio disponible en la memoria. Si se excede el tamaño máximo de la pila, puede ocurrir un desbordamiento de pila (stack overflow), lo que puede llevar a errores y fallos en el programa.

- **No admite búsqueda o ordenamiento eficiente:** Las pilas no son adecuadas para realizar operaciones de búsqueda o ordenamiento eficientes. 

---

## Usos

- Historial de navegación en un navegador web

- Manejo de deshacer y rehacer en editores de texto

- Evaluación de expresiones matemáticas

- Backtracking en algoritmos de búsqueda

</details>

<br>

<details>
<summary><b>🔍 Colas (Queues)</b></summary>

Imagina una fila de personas esperando en un banco. Cada vez que llega una nueva persona, se coloca al final de la fila, y cuando es su turno, se atiende y se retira de la fila. En este caso, el primero en llegar es el primero en ser atendido.

<br>

![Cola_de_banco](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.elfueguino.com.ar%2Fwp-content%2Fuploads%2F2016%2F08%2Ffila-banco.jpg&f=1&nofb=1&ipt=6440661f8953262b4f5c1c3699515a99bb61a498fc3735c925e426a286554c3a&ipo=images)

<br>

Una cola es una estructura de datos en la que los elementos se agregan al final y se eliminan desde el principio siguiendo el principio FIFO (First In, First Out).

>Las operaciones principales que se realizan en una cola son:
>
>- "Enqueue" (Encolar): Agregar un elemento al final de la cola.
>- "Dequeue" (Desencolar): Eliminar y retornar el elemento en el frente de la cola.
>- "Front" (Frente): Obtener el valor del elemento en el frente de la cola sin eliminarlo.
>- "Rear" (Final): Obtener el valor del elemento en el final de la cola sin eliminarlo.

<br>

## **Ventaja**

- **Ordenamiento justo:** Las colas siguen el principio FIFO, lo que significa que los elementos se procesan en el orden en que llegaron. Esto garantiza un ordenamiento justo y evita la posibilidad de que un elemento se quede esperando indefinidamente. 

- **Implementación sencilla:** Las colas son estructuras de datos relativamente simples de implementar y comprender. 

- **Uso eficiente de recursos:** Las colas se utilizan para gestionar recursos compartidos de manera eficiente. 

## **Desventajas**

- **Acceso limitado:** Al igual que con las pilas, las colas también tienen acceso limitado a los elementos. Solo se puede acceder y eliminar el elemento en el frente de la cola, lo que puede limitar la flexibilidad en ciertos casos.

- **Tamaño limitado:** Las colas también tienen un tamaño máximo fijo, lo que significa que hay una capacidad máxima para almacenar elementos en la cola. Si se supera este límite, puede ocurrir un desbordamiento de cola (queue overflow), lo que puede causar errores o fallas en el programa.

- **Complejidad en la búsqueda:** Si se necesita buscar un elemento específico en una cola, puede requerir un recorrido secuencial desde el frente hasta el final de la cola, lo que puede tener un tiempo de ejecución proporcional al tamaño de la cola.

---

## Usos

- Gestión de tareas

- Procesamiento de solicitudes

- Búfer de mensajes

- Algoritmos de búsqueda y recorrido

</details>



<br>
<br>
<br>

**No lineales:** Estas estructuras de datos no siguen una secuencia lineal y permiten la representación de relaciones más complejas entre los elementos. 

  - Arboles (Trees)

  - Grafos (Graphs)

  - Tablas de hash (Hash Tables)

<br>
<br>
<br>

# [*Algoritmos de ordenamiento*](2_AlgoritmosOrdenamiento.md)