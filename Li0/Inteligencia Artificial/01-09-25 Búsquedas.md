Campos según Turip
- Procesamiento del lenguaje natural
- Representación del conocimiento
- Visión computacional
- Aprendizaje automático
- Razonamiento automático
- Robótica inteligente

## ¿Qué es la Búsqueda en IA?
- En IA la búsqueda es un proceso fundamental para resolver problemas.
- Consiste en explirar un espacio de posibles soluciones para encontrar la mejor o más adecuada a un problema dado.
- Se utiliza cuando no existe un método directo para llegar a la solución, y se necesitar recorrer diferentes caminos has encontrarla.

Ejemplos Cotidianos
- Encontrar la *ruta más corta* en una aplicación de mapas.
- Resolver un *rompecabezas* como el cubo de Rubik
- Planificar los *movimientos óptimos* en un juego de ajedrez.

Búsqueda de la ruta más corta

## El Espacio de Estados
Todo problema de búsqueda se define por:
- *Estado inicial* el punto de partida.
- *Acciones* Los movimientos o transacciones permitidas.
- *Estados sucesores* Los nuevos estados que resultan de una acción.
- *Estado meta* El o los estados que representan la solución.

La representación más común es un árbol o grafo de búsqueda.

## Ejemplo Sencillo: De Cas a la Universidad

Búsqueda No informada
- *Problema:* Ir de casa a la universidad.
- *Estrategia* Probar todas las rutas posibles sin saber cuál es mejor.
- *Método* Explorar calle por calle hasta encontrar una que llegue.
- *Resultado* Tarde o temprano llegarás, pero no sabes si es la ruta más rápida.
Búsqueda Informada
- *Problema* Ir de casa a la universidad.
- *Estrategia* Usar información para tomar la mejor decisión.
- *Heurística* Un mapa con las distancias de cada calle.
- *Método* Elegir la ruta que parece más corta en cada cruce.
- *Resultado* Es muy probable que llegues más rápido  y eficientemente.

## De la Ruta a la Representación Computacional
La Necesidad de "Traducir" el problema
Para que una computadora pueda resolver el problema de encontrar la ruta más corta de casa a la universidad, necesita una manera de "entender" y manipular la información de las calles y los cruces.

- El mundo real, como las calles de una ciudad, se puede modelar como un *grafo*.
- En este modelo, los *nodos* representan los lugares (cruces, tu casa, la universidad).
- Los *arcos* (o aristas) representan las conexiones entre esos lugares (las calles o caminos)
El siguiente paso es ver cómo una computadora almacena esa estructura.

## Representación Matriz de adyacencia
Una matriz de adyacencia es una tabla cuadrada que utiliza valores binarios (0 o 1) para indicar la conexión entre nodos-
- Cada fila y columna representa un nodo del grafo.
- Un valor de 1 en la celda (i,j) significa que hay un arco del nodo i al nodo j.
- Un valor de 0 significa que no existe una conexión directa
Vecino

|     | *1* | *2* | *3* |
| --- | --- | --- | --- |
| *1* | 0   | 1   | 1   |
| *2* | 1   | 0   | 0   |
| *3* | 1   | 0   | 0   |
## Representación Lista de Adyacencia
Una lista de adyacencia es un arreglo donde cada posición (índice) se asocia con un nodo. Cada posición contiene un alista con los nodos vecinos de ese nodo.
- Es más eficiente en memoria para grafos dispersos (con pocos arcos).
- La información está organizada de manera que es fácil encontrar los vecinos de un nodo específico.

Lista de adayacencia
[[2,3],[1],[1]]

Representación


| Nodo | Vecinos |
| ---- | ------- |
| 1    | 2,3     |

## Tipos de Estrategias de Búsqueda
1. **Búsquedas no Informadas (Ciegas)**
	1. No utilizan conocimiento adicional del problema
	2. Exploran el espacio de estados de manera sistemática
	3. *Ejemplo:* Recorrer todas las calles de una ciudad hasta encontrar una dirección.
	4. *Algoritmos típicos*
		1. Búsqueda en *amplitud* (BFS)
		2. Búsqueda en *profundidad* (DFS)
		3. Búsqueda *Exhaustiva*
2. **Búsquedas informadas (heurísticas)*
	1. Usan *información extra* (heurísticas) para guiar la búsqueda.
	2. La heurística es una función que estaima la "cercanía a la meta"
	3. *Ejemplo:* Usar un mapa para elegir la ruta más corta.
	4. *Algoritmos típicos:*
		1. Búsqueda *Greedy (Voraz)*
		2. Algoritmo *a** (A-star)
		3. *Ramificación y Poda*

## Criterios de Comparación
- Para evaluar la eficiencia de un algoritmo de búsqueda, consideramos
- *Completitud* ¿El algoritmo siempre encuentra una solución si esta existe?
- *Optimalidad* ¿El algoritmo garantiza encontrar la mejor solución (la más corta, la más barata, etc).
- *Complejidad en Tiempo* ¿Cuánto tiempo tarda en ejecutarse el algoritmo? (Medido en números de pasos).
- *Complejidad en Espacio* ¿Cuánta memoria o espacio de almacenamiento necesita el algoritmo?

## Búsqueda en Amplitud (BFS)
BFS (Breadth-First Search) explora el espacio de búsqueda nivel por nivel. Primero visita todos los nodos a un paso del inicio, luego todos los nodos a dos pasos, y así sucesivamente.

*Analogía* Piensa en una onda que se expande desde el centro de un lago. Explora todas las orillas más cercanas antes de llegar a las que están más lejos.
- *Optimalidad* Garantiza encontrar la ruta más corta en términos de número de pasos.
- *Complejidad en espacio* Puede ser muy costoso en memoria si el ancho del árbol de búsqueda es grande.
## Actividad BFS es un Laberinto
Objetivo
Simular BFS para encontrar la ruta más corta en un laberinto.
- Materiales: Pizarra cuadricula, marcadores de colores.
- Instrucciones:
	- Dibuja una cuadrícula de 5x5 con un Inicio y una Meta
	- El equipo marca el Inicio (nivel 0) con un color.
	- Con otro color, marcan todos los nodos adyacentes (Nivel 1)
	- Repiten el proceso para el nivel 2 y los siguientes, hasta que la meta sea marcada.
Reflexión
¿Por qué el primer camino que encuentra BFS es el más corto?

