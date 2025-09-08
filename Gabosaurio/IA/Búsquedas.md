- En la IA, la búsqueda es un proceso fundamental para resolver problemas
- Consiste en explorar un espacio de posibles soluciones para encontrar la mejor o más adecuada a un problema dado
- Se utiliza cuando no existe un método directo para llegar a la solución y se necesita recorrer diferentes caminos hasta encontrarla
## Ejemplos cotidianos
- Encontrar la ruta más corta en una aplicación de mapas
- Resolver un rompecabezas como el cubo de Rubik
- Planificar los movimientos óptimos en un juego de ajedrez
## Elementos clave
Todo problema de búsqueda se define por:
- **Estado inicial:** El punto de partida
- **Acciones:** Los movimientos o transiciones permitidas
- **Estados sucesores:** Los nuevos estados que resultan en una acción
- **Estado meta:** El o los estados que representan la solución
- La representación más común es un árbol o grafo de búsqueda

## Ejemplo sencillo: De casa a la Universidad
### Búsqueda no informada
- Problema: Ir de casa a la universidad
- Estrategia: Probar todas las rutas posibles sin saber cuál es mejor
- Método: Explorar calle por calle hasta encontrar una que llegue
- Resultado: Tarde o temprano llegarás, pero no sabes si es la ruta más rápida
### Búsqueda informada
- Problema: Ir de casa a la universidad
- Estrategia: Usar información para tomar la mejor decisión
- Heurística: Un mapa con las distancias de cada calle
- Método: Elegir la ruta que parece más corta en cada cruce
- Resultado: Es muy probable que llegues más rápido y eficientemente
## De la Ruta a la Representación Computacional
### La necesidad de "Traducir" el problema
Para que una computadora pueda resolver el problema de encontrar la ruta más corta de casa a la universidad, necesita un amanera de "entender" y manipular la información de las calles y los cruces
- El mundo real, como las calles de una ciudad, se puede modelar un grafo
- En este modelo, los nodos representan los lugares (cruces, tu casa, la universidad)
- Los arcos (o aristas) representan las conexiones entre esos lugares (las calles o caminos)
**El siguiente paso es ver cómo una computadora almacena esta estructura**

### Representación Computacional
#### Nuestro problema
Para entender cómo se representa un grafo, utilizaremos un ejemplo sencillo.
**Grafo, nodos y arco**
![[IMG_20250901_135422123~2.jpg|85x125]]
#### Matriz de adyacencia
Una matriz de adyacencia es una tabla cuadrada que utiliza valores binarios (0 o 1) para indicar la conexión entre nodos
- Cada fila y columna representa un nodo
- Un 1 significa que hay relación del nodo de la columna con el de la fila
- Un valor 0 significa que no hay conexión
#### Lista de adyacencia
Una lista de adyacencia es un arreglo donde cada posición (índice) se asocia con un nodo. Cada posición contiene una lista con los nodos vecinos de ese nodo
- Es más eficiente en memoria para grafos **dispersos** (con pocos arcos)
- La información está organizada de manera que es fácil encontrar los vecinos de un nodo específico
Ejemplo
[[[2,3], [1], [1]]]
## Tipos de estrategias de búsqueda
### Búsquedas no informadas (ciegas)
- No utilizan conocimiento adicional del problema
- Exploran el espacio de estados de manera sistemática
- Algoritmos típicos:
	- Búsqueda de Amplitud (BFS)
	- Búsqueda de Profundidad (DFS)
	- Búsqueda Exhaustiva
### Búsquedas informadas (Heurísticas)
- Usan información extra (heurísiticas) para guiar la búsqueda
- La heurística es una función que estima la "cercanía" a la meta
- Algoritmos típicos:
	- Búsqueda Greedy (Voraz)
	- Algoritmo A* (A-star)
	- Ramificación y Poda
## Criterios de comparación
- Para evaluar la eficiencia de un algoritmo de búsqueda, consideramos:
	- **Completitud:** ¿El algoritmo siempre encuentra una solución si está existe?
	- **Optimalidad:** ¿El algoritmo garantiza encontrar la mejor solución (la más corta, la más barata, etc.)?
	- **Complejidad en tiempo:** ¿Cuánto tiempo tarda en ejecutarse el algoritmo? (Medido en número de pasos)
	- **Complejidad en Espacio:** ¿Cuánta memoria o espacio de almacenamiento necesita el algoritmos
# Búsqueda en Amplitud (BFS)
BFS (Breadth-First Search) explora el espacio de búsqueda nivel por nivel. Primero visita todos los nodos a un paso del inicio, luego todos los nodos a dos pasos y así sucesivamente
Piensa en una onda que se expande desde el centro de un lago. Explora todas las orillas más cercanas antes de llegar a las que están más lejos
- **Optimalidad:** Garantiza encontrar la ruta más corta en términos de números de pasos
- **Complejidad en espacio:** Puede ser muy costoso en memoria si el ancho del árbol de búsqueda es grande
¿Por qué el primer camino que encuentra BFS es el más corto?
	Porque como va por conexiones entre nodos, el más largo requerirá hacer más de estas y se espera que se llegue a la meta antes

## Pseudocódigo
### Idea principal
- BFS utiliza una estructura de datos llamada cola para explorar los nodos de manera ordenada, garantizando que los nodos más cercanos al origen sean visitados primero
### Variables clave
- Cloa: FIFO, para almacenar los nodos por explorar
- Visitados: Un conjunto o lista para evitar ciclos y no visitar el mismo nodo dos veces
### 1. Preparación
Antes de comenzar el algoritmo necesita crear las herramientoas para su búsqueda
```
	FUNCION BFS(Grafo, Inicio)
		Crear Cola vacia
		Crear conjunto visitados
```
Cola: Funciona como una lista de espera. Los nodos se añaden al final y se retiran del principio (FIFO).  Esto asegura que exploremos los nodos en el orden en que los encontramos, de los más cercanos a los más lejanos
Conjutno visitados: Un registro de todos los nodos que ya hemos explorado. Su propósito es evitar ciclos y no procesar el mismo nodo másd e una vez, lo que podría hacer la búsqueda infinita
### 2. El bucle principal
El corazón del algoritmo. Mientras haya nodos por explorar en la cola, el proceso continúa.
```
MIENTRAS Cola no este vacia HACER
	Nodo = Desencolar(Cola)
	Procesar(Nodo) //Ej: imprimirlo
FIN_MIENTRAS
```
Desencolar: Se toma el primer nodo de la cola. Este es siempre el nodo más antiguo y el más cercano al inicio de la búsqueda, lo que garantiza el comportamiento "en amplitud"
Procesar: En este punto, el algoritmo realiza alguna acción con el nodo (por ejemplo, gerificar si es la meta, imprimir su nombre, etc)
### 3. La expansión de Nodos
Después de procesar un nodo, el algoritmo busca sus vecinos para continuar la exploración
```
PARA CADA vecino EN Vecinos(Nodo) HACER
	SI Vecino NO esta en Visitados ENTONCES
		Encolar(Vecino)
		Agregar(Vecino, Visitados)
	FIN_SI
FIN_PARA
```
Verificación: Para cada vecino del nodo actual, se verifica si ya ha sido visitado. Si no lo ha sido, se considera un nuevo nodo a explorar.
Añadir a la cola: El nuevo vecino se añade a la cola. Esto asegura que se procesará en un futuro, pero solo después de que todos los nodos de su mismo nivel de distancia hayan sido explorados

## Pseudocódigo completo
```
	FUNCION BFS(Grafo, Inicio)
		Crear Cola vacia
		Crear conjunto visitados
		MIENTRAS Cola no este vacia HACER
			Nodo = Desencolar(Cola)
			Procesar(Nodo) //Ej: imprimirlo
		FIN_MIENTRAS
		PARA CADA vecino EN Vecinos(Nodo) HACER
			SI Vecino NO esta en Visitados ENTONCES
				Encolar(Vecino)
				Agregar(Vecino, Visitados)
			FIN_SI
		FIN_PARA
```