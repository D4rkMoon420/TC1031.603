# Proyecto: Simulador de base de datos de NBA
> Los datos de este proyecto son obtenidos de la página (https://www.basketball-reference.com/leagues/NBA_2023.html#all_per_game_team-opponent) y se basa en su manera de ordenar listas.  
> El Programa te da la opción de: 
1. Imprimir los datos del csv (tabla de posciones).
2. Ordenar los datos con el algoritmo de merge sort.
3. Buscar por nombre de equipo utilizando el algoritmo de busqueda lineal.
4. Acceder a un elemento de los datos por su numero de ranking utilizando una estructura de datos de árbol de búsqueda binaria.
5. Insertar nuevo equipo tanto al árbol como al vector.
6. Al salir del programa se crea o se sobrescribe (si ya existe el .txt 'reporteNBA') un archivo de texto donde se muestra la tabla de posiciones, incluyendo equipos agregados al simulador. 

## Descripción del avance 1
> Contiene la implementación del algoritmo de ordenamiento merge sort para ordenar por porcentaje de 3 puntos y 2 puntos ,y el algoritmo de busqueda lineal para encontrar al equipo deseado por el usuario. 

## Descripción del avance 2
> Contiene la implementación de la estructura de datos árbol de búsqueda binaria (BST) para encontrar el número de ranking al que el usuario desea acceder, también se implementa la función para insertar elementos al BST y después evaluarlo en el mismo. 

### Cambios sobre el primer avance
1. Cambio 1: Se utiliza un BST para la opción "Acceder por numero de ranking" en lugar de un algoritmo de busqueda lineal. Esto se hace con la finalidad de hacer más eficiente la búsqueda del elemento númerico.
  
2. Cambio 2: Se cambia el nombre a "Simulador de base de datos de NBA". Esto debido a que la implementación de una opción "Insertar nuevo equipo" hace que la idea principal del objetivo cambie para que el usuario pueda crear su propia base de datos y poder compararla y analizarla como la de la NBA.

3. Cambio 3: Se implementa un método insert() para agregar equipos al BST con los datos originales y al mismo tiempo se suma al vector principal que contiene la tabla de posiciones para poder analizarlo con los datos originales de la NBA.

4. Cambio 4: Se agregan dos archivos: bst.h y su respectivo bst.cpp, donde se implementa la clase BST que permite la incorporación del árbol de búsqueda binaria. 

## Descripción del avance 3
En este avance se implementa la función para leer los datos del equipo que se agregaron, externos a la base de datos para después incluirlos en la impresión final. Para esto se utilizó la libreria <fstream>.

### Cambios sobre el segundo avance
El único cambio fue la implementación de escritura de datos en un archivo externo al finalizar el programa.

## Instrucciones para compilar el avance de proyecto
> Ejecuta el siguiente comando en la terminal:

`g++ bst.h bst.cpp NBAdata.h NBAdata.cpp main.cpp -o nba` 

## Instrucciones para ejecutar el avance de proyecto
Ejecuta el siguiente comando en la terminal:

`./nba` 

> Presiona el botón: 
`Run`

## Descripción de las entradas del avance de proyecto
Entrada: archivo llamado (nba_data.csv)
         formato: comma separated values (csv)
         ejemplo: 1,Sacramento Kings,0.369,0.586,43.6,88.2,0.494,13.8,37.3,82,29.8,50.9,241.8,19.8,25.1,0.79,9.5,32.9,42.5,27.3,7,3.4,13.5,19.7,120.7 (en el programa no se utilizan todas las variables), se utilizan las primeras cuatro (ranking, nombre, %3P, %2P)

## Descripción de las salidas del avance de proyecto
> Ejemplo 1:
> Paso 1: seleccionar la opción deseada en el menú, en este caso 5, (Insertar nuevo equipo).
> Paso 2: ingresar nombre del equipo a insertar, en este caso "Huskies".
> Paso 3: ingresar porcentaje de triples del equipo a insertar, en este caso "0.50".
> Paso 4: ingresar porcentaje de tiros de dos puntos del equipo, en este caso "0.50".
> Paso 5: el sistema mostrará un mensaje de confirmación de equipo insertado
> Paso 6: regresa al menú principal y seleccionar otra opción, en este caso 1 (Mostrar tabla de posiciones y datos), para corroborar que nuestro equipo fue insertado, con esto nos aseguramos que nuestro equipo podrá ser analizado y ordenado por las opciones programadas en el avance 1.
> Paso 7: regresa al menú principal y seleccionar otra opción, en este caso 4 (Acceder por numero de ranking).
> Paso 8: ingresar número de ranking del equipo al que desea acceder el usuario, en este caso "31", para acceder a nuestro equipo añadido previamente y ver sus estadísticas.
> Paso 9: regresa al menú principal y seleccionar otra opción, en este caso 0 (Salir).
> Fin del programa, se muestra "Gracias vuelva pronto".
> Al finalizar el programa se crea un archivo de texto llamado 'reporteNBA.txt' en el cual se muestra la tabla de posiciones final con el equipo 'Huskies' agregado al final de la tabla. 

## Desarrollo de competencias

### SICT0301: Evalúa los componentes
#### Hace un análisis de complejidad correcto y completo para los algoritmos de ordenamiento usados en el programa.
> Merge sort O(n log n): el bucle externo en merge sort se ejecuta O(log n) veces, esto se debe a que en cada iteración, el tamaño del vector se divide aproximadamente a la mitad. También se realizan divisiones y fusiones repetidas, estas se ejecutan en O(n) debido a que dentro de la función auxiliar se copian elementos en vectores temporales y luego se combinan en un solo vector ordenado, Por lo que la combinación de O(log n) y O(n) = O(n log n)

#### Hace un análisis de complejidad correcto y completo de todas las estructuras de datos y cada uno de sus usos en el programa.
>   Buscar :  se basa en la busqueda binaria por lo tanto implica dividir el árbol en aproximadamente la mitad en cada paso lo que en promedio encuentra los elementos con una complejidad de O(log n).Sin embargo en el peor de los casos, si el árbol esta desequilibrado se convierte en una lista ligada por lo tanto la complejidad es de O(n).
>   Inserción: si el árbol esta equilibrado tiene complejidad de O(log n) debido a que cada inserción se realiza dividiendo el árbol en aproximadamente la mitad, ya que se compara el valor a insertar con los valores en los nodos para decidir si irá a la izquierda o derecha. si el árbol esta desequilibrado se convierte en una lista ligada por lo tanto la complejidad es de O(n).

#### Hace un análisis de complejidad correcto y completo para todos los demás componentes del programa y determina la complejidad final del programa.
**Ordenamiento:**
>   Merge sort O(n log n): el bucle externo en merge sort se ejecuta O(log n) veces, esto se debe a que en cada iteración, el tamaño del vector se divide aproximadamente a la mitad. También se realizan divisiones y fusiones repetidas, estas se ejecutan en O(n) debido a que dentro de la función auxiliar se copian elementos en vectores temporales y luego se combinan en un solo vector ordenado, Por lo que la combinación de O(log n) y O(n) = O(n log n) 221-317 NBAdata.cpp

**Estructuras de datos (BST):**
>   Buscar por ranking:  se basa en la busqueda binaria por lo tanto implica dividir el árbol en aproximadamente la mitad en cada paso lo que en promedio encuentra los elementos con una complejidad de O(log n).Sin embargo en el peor de los casos, si el árbol esta desequilibrado se convierte en una lista ligada por lo tanto la complejidad es de O(n). 37-49 bst.cpp
>   Inserción de equipo: si el árbol esta equilibrado tiene complejidad de O(log n) debido a que cada inserción se realiza dividiendo el árbol en aproximadamente la mitad, ya que se compara el valor a insertar con los valores en los nodos para decidir si irá a la izquierda o derecha. si el árbol esta desequilibrado se convierte en una lista ligada por lo tanto la complejidad es de O(n). 9-35 bst.cpp

**Main:**
>   Lectura de datos O(n * L): donde n es el numero de lineas en el archivo y L es la longitud de cada línea ya que dentro del bucle principal, cada llamada a get line es O(L), por la longitud de la línea y se repite n veces. 16-38 main.cpp
>   Escritura de datos O(n): donde n es el numero de datos en el vector ya que dentro del bucle for se recorren cada uno de los datos dentro del vector. 43-52 main.cpp

**Menu:**
>   Mostrar menu O(1): ya que la función es constante, es decir, siempre que se manda a llamar tarda lo mismo y tampoco incluye bucles. 89-99 NBAdata.cpp
>   Gestionar menu: incluye todas las implementaciones de cada una de las opciones, por lo tanto:
- Caso 0: salida del menu O(1)
- Caso 1: mostrar datos O(n), depende de los elementos del vector 
- Caso 2: ordenar datos O(n log n), utiliza merge sort
- Caso 3: buscar equipo O(n) 
- Caso 4: acceso por ranking O(log n) promedio y O(n) en el peor de los casos ya que utiliza busqueda en un BST
- Caso 5: insertar equipo O(log n) promedio y O(n) peor de los casos ya que se inserta mediante el arbol e insertarlo al vector O(1)
- El ciclo while en el que esta el menu depende del usuario
101-219 NBAdata.cpp

**Otros métodos:**
>   Buscar por nombre O(n * L): donde n es el numero de equipos en el vector y L es la longitud promedio de los nombres. En el mejor de los casos sería O(L) ya que sólo tendria que hacer la comparación una vez de si es el equipo que se busca. 56-74 NBAdata.cpp
>   Pasar a minúscula O(n): donde n es el numero de caracteres en el string de entrada. 319-326 main.cpp

**Complejidad total del programa:**
> La complejidad total del programa seria O(n log n), gracias a que el metodo mas complejo es el merge sort y su complejidad es esa. Por lo que el peor de los casos del programa en una sola ejecución es O(n log n) pero depende de las acciones del usuario. 

### SICT0302: Toma decisiones
#### Selecciona un algoritmo de ordenamiento adecuado al problema y lo usa correctamente.
> Para este programa utilice un algoritmo de tipo merge sort, para poder organizar los datos de mayor a menor en base al criterio (porcentaje de 2P o porcentaje de 3P). Use merge sort porque tiene una complejidad aceptable y constante en todos los casos lo cual lo hace el mejor algoritmo para conjuntos de datos grandes. Las funciones donde se puede ver es en mergeSort(), mergeSortBy2Ppercent() y mergeSortBy3Ppercent() en las lineas 221-317 del archivo NBAdata.cpp

#### Selecciona una estructura de datos adecuada al problema y la usa correctamente.
> Para este programa utilice un árbol de búsqueda binario (BST) como estructura de datos para poder buscar rapidamente a un equipo por su ranking y poder insertar nuevos equipos al arbol. Use el BST debido a su eficiencia para la búsqueda, inserción y ordenamiento de datos.  El BST es especialmente eficiente para buscar elementos según un criterio específico. En mi proyecto la busqueda es en base al ranking por lo que mientras el arbol este equilibrado se encontrara el equipo eficientemente. Las funciones donde se puede observar es en  insert() y searchByRanking() en las líneas 9-49 del archivo bst.cpp

### SICT0303: Implementa acciones científicas
#### Implementa mecanismos para consultar información de las estructras correctos.
La implementación de un BST permite consultar información de los equipos. El método de búsqueda por ranking esta diseñado para acceder e imprimir la información del equipo buscado por número de este, también mantiene los datos organizados según el mismo, lo que facilita la consulta y presentación de información relacionada con la clasificación de equipos de la NBA, aunque también se puede ordenar por otros factores. La consulta e impresión de los datos se puede ver en las líneas 174-186 del NBAdata.cpp

#### Implementa mecanismos de lectura de archivos para cargar datos a las estructuras de manera correcta.
La implementación de mecanismos de lectura de archivos se puede ver en las líneas 16-38 del archivo main.cpp en el que se leen los datos de un archivo csv y se extraen sólo algunos datos  con los que se trabajan en el proyecto. La función getline() nos ayuda a recorrerlo y extraer. Para meter los datos en un vector y poder visualizarlos se utiliza push_back(). Para meter los datos al BST utilizamos "this->" en la declaración del constructor de la clase NBAdata y asi podemos crear un objeto de tipo NBAdata y asignarlo al nodo para despues insertarlo al árbol

### Implementa mecanismos de escritura de archivos para guardar los datos  de las estructuras de manera correcta
La implementación de mecanismos de escritura de archivos se puede ver en las líneas 43-52 del archivo main.cpp en el que recorremos el vector "NBAData" e imprimimos los datos en el txt.