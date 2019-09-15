En este archivo obtendrá un pequeño resumen de como está dividido el código, de como ejecutar el código para que usted pueda realizar cambios para probar los ejemplos que desee, entre otras cosas.

Comencemos con el primer apartado "Presentacion_Ej1".
--------------------
 Resumen del código
--------------------
Lo primero que nos encontramos son las bibliotecas necesarias para nuestro proyecto, vamos a explicar brevemente las bibliotecas que no hemos usado durante el curso: timeit (que la usaremos para saber el tiempo de ejecución de los distintos métodos de búsqueda de estados), random (lo usamos para generar piezas de manera aleatoria), numpy (nos servirá para hacer rotaciones de matrices en algunos métodos auxiliares).
Luego tenemos dos matrices, la primera nos servirá para la métodos de 'Acciones' y la otra matriz('mapa_inicial'), la usaremos para el resto de métodos.
Empezamos creando las piezas que usaremos en el juego y la posición inicial donde aparecerán en la matriz, después tenemos dos métodos auxiliares para rotar a izquierda o derecha las piezas creadas anteriormente. Continuamos con los métodos de 'Acciones', los cuales sirven para desplazar Abajo,Izquierda,Derecha o girar la pieza a Izquierda o Derecha. Luego tenemos la creación del problema donde indicamos las acciones, estado inicial, estado final para el mejor camino.
Y por último, nos encontramos con los distintos métodos de búsqueda de estados con los que obtendremos el camino para llegar desde el estado inicial al estado final. Así como el tiempo de ejecución de cada método de búsqueda, los métodos probados son: búsqueda en anchura, primero el mejor, óptima, A* (a_estrella) y en profundidad(este último sin exito, ya que entra en un bucle infinito, y se tiene que interrumpir la ejecución).

-------------------------
 Ejecución y experimento 
-------------------------
Nosotros hemos usado Jupyter Notebook como entorno interactivo web, y como lenguaje de programación Python en la versión 3.6.2.
Para ejecutar el proyecto entero se puede ejecutar celda a celda el botón 'Run' o pulsar en 'Cell' y luego 'Run All'. Si realiza la segunda opción, obtendrá cada celda de manera ordenada y podrá seguir correctamente las explicaciones para realizar usted mismo las pruebas que desee.

Una vez ejecutadas todas las celdas, ya podemos experimentar con el ejercicio.
    -Podemos modificar las matrices de las celdas [4] y [5], siempre han de tener el mismo valor, para tener distintas situaciones.
     En la celda [3], se explica que un 1 corresponde con una celda ocupada y un 0 corresponde con una celda vacia.
    -Podemos cambiar los valores del estado_inicial y estado_final1 en la celda [10] para llegar desde un punto a otro.
     El orden del array debe estar siempre ordenado de menor valor a mayor valor(de arriba hacia abajo y de izquierda a derecha, 
     ej_correcto: [[0, 3], [0, 4], [1, 3], [1, 4]]   ej_erróneo:  [[0, 3], [1, 3], [0, 4], [1, 4]]).
     Además para que el resultado sea válido y tenga una solución debe ser coherente, ya que se simula que las celdas de la pieza estan 
     unidas unas a otras, por tanto no valdría el siguiente ejemplo: [[17, 4], [1, 3], [1, 9], [18, 5]].
     
Luego ejecutariamos los distintos métodos de búsqueda para ver los resultados y sus tiempos.
Por tanto ejecutaríamos celdas [4] y [5](solamente si cambiamos el mapa), la celda [10] donde cambiamos el estado_inicial y estado final. Y los métodos de búsqueda que comienza en la celda[23] en adelante.



Sigamos con el segundo apartado "Presentacion_Ej2"
--------------------
 Resumen del código
--------------------
En el segundo apartado, reutilizaremos código del primer apartado, ya que es una extensión del anterior.Hasta la celda [11] (incluida), es el mismo código que usamos antes. Luego nos encontramos con unos métodos auxiliares que utilizaremos en los 36 métodos de posibles estados finales para una pieza. Los métodos para probar los posibles estados finales son prácticamente iguales, solo cambian dos o tres cosas superficiales, por lo que viendo un método entenderás el resto. 
Después tenemos un método heuristico para calcular la mejor posición posible, penalizando una la altura ponderada alta, y que provoque un hueco al caer la pieza, por el contrario penalizamos en positivo que una pieza provoque un borrado de linea, para eliminar así el mayor número de lineas posibles.
A continuación metemos en una lista todas las soluciones posibles y devolvemos la mejor solución. Por último, introducimos la solución en el mapa_inicial, y con la búsqueda de anchura nos proporcionará las acciones que hemos realizado para llegar a esa posición.


-------------------------
 Ejecución y experimento 
-------------------------
Nosotros hemos usado Jupyter Notebook como entorno interactivo web, y como lenguaje de programación Python en la versión 3.6.2.
Para ejecutar el proyecto entero se puede ejecutar celda a celda el botón 'Run' o pulsar en 'Cell' y luego 'Run All'. Si realiza la segunda opción, obtendrá cada celda de manera ordenada y podrá seguir correctamente las explicaciones para realizar usted mismo las pruebas que desee.

Una vez ejecutadas todas las celdas, ya podemos experimentar con el ejercicio.
    -Podemos modificar las matrices de las celdas [4] y [5], siempre han de tener el mismo valor, para tener distintas situaciones.
     En la celda [3], se explica que un 1 corresponde con una celda ocupada y un 0 corresponde con una celda vacia.
    -Podemos cambiar el valor de normal en la celda [16], como explicamos en el apartado 1, el valor de normal debe seguir unas normas para
    que no exista problemas.
    
Por tanto ejecutaríamos celdas [4] y [5](solamente si cambiamos el mapa), la celda [16] donde cambiamos el valor de la variable 'normal'.
Y las celdas [17],[18],[19] para ver las acciones que dan lugar a colocar la pieza en esa posición.



Terminamos con el tercer apartado "Presentacion_Ej3"
--------------------
 Resumen del código
--------------------
En el último apartado, usamos métodos que utilizamos en el apartado anterior más los situados en las celdas [13],[14],[15],[16] y [21], es última corresponde con la celda que utilizaremos para jugar. Los métodos del 13 al 16 los usamos para borrar la linea que tenga solamente 1's, y desplazar las lineas por encima del borrado hasta que encuentre una celda ocupada(que valga 1).
La última celda, es la que contiene todos los métodos necesarios para jugar al tetris. Al ejecutarla nos preguntará si deseamos jugar, en caso afirmativo poner 'S', en caso contrario marcar 'N' para parar el juego. Por cada caso afirmativo se nos devolverá la pieza randomizada que se inserta en el mapa, la mejor posición para colocarla, las acciones que han ocurrido para llegar a ese punto y como quedaría el mapa tras insertar la pieza en la posición final(mejor posición).


-------------------------
 Ejecución y experimento 
-------------------------
Nosotros hemos usado Jupyter Notebook como entorno interactivo web, y como lenguaje de programación Python en la versión 3.6.2.
Para ejecutar el proyecto entero se puede ejecutar celda a celda el botón 'Run' o pulsar en 'Cell' y luego 'Run All'. Si realiza la segunda opción, obtendrá cada celda de manera ordenada y podrá seguir correctamente las explicaciones para realizar usted mismo las pruebas que desee.

Una vez ejecutadas todas las celdas nos saldrá un mensaje para seguir jugando al juego o parar,si deseas realizar cambios en la partida, deberás cancelarla primero, escribiendo 'N' en el mensaje que aparece, luego ya podemos experimentar con el ejercicio.
    -Podemos modificar la matriz [5] (mapa_inicial).
    -Podemos modificar la celda [8], para colocar el número de piezas que queremos crear.
     Código:    for i in range(-Colocar número de piezas que desee crear-):
     
     


