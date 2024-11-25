# Proyecto: Simulador de Base de Datos de NBA
> Este proyecto utiliza datos extraídos de la página [basketball-reference](https://www.basketball-reference.com/leagues/NBA_2023.html#all_per_game_team-opponent) siguiendo su formato de organización de listas.  
> El programa ofrece las siguientes funcionalidades:  
1. Mostrar los datos del archivo CSV (tabla de posiciones).  
2. Ordenar los datos mediante el algoritmo merge sort.  
3. Buscar un equipo por nombre utilizando búsqueda lineal.  
4. Acceder a un equipo por su ranking mediante una estructura de árbol de búsqueda binaria (BST).  
5. Insertar un nuevo equipo tanto en el árbol como en el vector.  
6. Al salir del programa, se genera o sobrescribe un archivo de texto llamado 'reporteNBA.txt', que incluye la tabla de posiciones actualizada con los equipos añadidos durante la ejecución.

## Descripción del avance 1
> Este avance implementa el algoritmo de ordenamiento merge sort para clasificar equipos según sus porcentajes de tiros de tres y dos puntos, así como el algoritmo de búsqueda lineal para localizar equipos específicos por nombre.  

## Descripción del avance 2
> Aquí se introduce una estructura de datos de árbol de búsqueda binaria (BST), utilizada para localizar equipos por su ranking. Además, se implementa la funcionalidad de insertar nuevos equipos al árbol y evaluarlos dentro del mismo.  

### Cambios respecto al primer avance  
1. **Cambio 1:** Se reemplaza el uso de búsqueda lineal para la opción de "Acceder por número de ranking" por un BST, mejorando la eficiencia al realizar la búsqueda numérica.  
2. **Cambio 2:** El nombre del proyecto se modifica a "Simulador de Base de Datos de NBA" para reflejar mejor el objetivo de permitir al usuario crear, analizar y comparar una base de datos personalizada con la de la NBA.  
3. **Cambio 3:** Se implementa un método `insert()` que permite añadir equipos al BST y al vector principal, manteniendo los datos disponibles para análisis posteriores.  
4. **Cambio 4:** Se crean dos nuevos archivos: `bst.h` y `bst.cpp`, en los que se define e implementa la clase BST, habilitando las funcionalidades relacionadas con los árboles de búsqueda binaria.  

## Descripción del avance 3
> En este avance, se añade la función de lectura de datos externos, como los equipos añadidos durante la ejecución, para incluirlos en la impresión final. Se emplea la biblioteca `<fstream>` para realizar esta tarea.  

### Cambios respecto al segundo avance  
El único cambio relevante es la incorporación de la escritura en un archivo externo al finalizar el programa.  

## Instrucciones para compilar el avance del proyecto  
Ejecutar el siguiente comando en la terminal:  
`g++ bst.h bst.cpp NBAdata.h NBAdata.cpp main.cpp -o nba`  

## Instrucciones para ejecutar el avance del proyecto  
Ejecutar el siguiente comando en la terminal:  
`./nba`  

> Posteriormente, interactúa con el menú a través de las opciones disponibles.  

## Descripción de las entradas del avance del proyecto  
Entrada: Archivo llamado `nba_data.csv`.  
Formato: Valores separados por comas (CSV).  
Ejemplo:  
`1,Sacramento Kings,0.369,0.586,43.6,88.2,0.494,13.8,37.3,82,29.8,50.9,241.8,19.8,25.1,0.79,9.5,32.9,42.5,27.3,7,3.4,13.5,19.7,120.7`.  
En este proyecto solo se utilizan las primeras cuatro variables: ranking, nombre, porcentaje de tiros de tres puntos (%3P) y porcentaje de tiros de dos puntos (%2P).  

## Descripción de las salidas del avance del proyecto  
**Ejemplo:**  
1. Selecciona la opción 5 (Insertar nuevo equipo) en el menú.  
2. Ingresa el nombre del equipo, por ejemplo, "Huskies".  
3. Ingresa el porcentaje de triples, por ejemplo, "0.50".  
4. Ingresa el porcentaje de tiros de dos puntos, por ejemplo, "0.50".  
5. Recibirás un mensaje confirmando que el equipo fue agregado.  
6. Regresa al menú principal y selecciona la opción 1 (Mostrar tabla de posiciones).  
7. Verifica que el equipo se agregó correctamente.  
8. Regresa al menú y selecciona la opción 4 (Acceder por número de ranking).  
9. Ingresa el ranking del equipo agregado, por ejemplo, "31".  
10. Verifica que los datos del equipo sean correctos.  
11. Sal del programa seleccionando la opción 0.  
12. Al finalizar, se genera el archivo `reporteNBA.txt` con la tabla de posiciones actualizada, incluyendo el equipo "Huskies".  

---

### Desarrollo de competencias  

#### **SICT0301: Evalúa los componentes**  
**Análisis de complejidad de algoritmos de ordenamiento:**  
> El algoritmo merge sort tiene una complejidad de \(O(n \log n)\), ya que divide el conjunto de datos en mitades \(O(\log n)\) y luego combina las mitades en \(O(n)\). La complejidad total es la combinación de estos procesos.  

**Análisis de estructuras de datos (BST):**  
- **Búsqueda:** \(O(\log n)\) en promedio, ya que divide el árbol en mitades. En el peor de los casos, un árbol desbalanceado tiene complejidad \(O(n)\).  
- **Inserción:** También \(O(\log n)\) promedio y \(O(n)\) en el peor caso si el árbol está desbalanceado.  

**Complejidad del programa:**  
> La operación más costosa es el merge sort (\(O(n \log n)\)). Sin embargo, la complejidad global depende de las acciones del usuario y puede variar según el caso.  

---  

#### **SICT0302: Toma decisiones**  
**Elección de algoritmos y estructuras de datos:**  
- Merge sort se seleccionó por su desempeño consistente en conjuntos grandes.  
- El BST se empleó para optimizar búsquedas y facilitar inserciones, especialmente al trabajar con rankings.  

---

#### **SICT0303: Implementa acciones científicas**  
**Mecanismos de lectura y escritura:**  
- La lectura de datos CSV emplea `getline` para extraer información y cargarla en estructuras adecuadas como vectores y nodos de árboles.  
- La escritura se realiza mediante `ofstream` para generar un archivo con la tabla de posiciones actualizada.  

