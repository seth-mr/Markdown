


### DFS (Depth-First Search)

El **DFS (Búsqueda en Profundidad)** explora un camino tan profundo como sea posible antes de retroceder y explorar otra rama.  

Se puede interpretar como un **explorador de cuevas** que sigue un solo túnel hasta el final.  
Si no encuentra lo que busca, regresa al último cruce para tomar otra dirección.  

Es un algoritmo *óptimo* y de *bajo uso de memoria*.  

---

### Pasos del algoritmo DFS

#### 1. Preparación de la búsqueda
1. Definir la función `DFS(inicio)`.  
2. Crear una **pila vacía**.  
3. Crear un **conjunto de visitados**.  

- La **pila** funciona como una pila de platos: los nodos se añaden y se retiran del mismo lugar.  
- Esto asegura que la búsqueda se adentre lo más posible en una rama antes de retroceder.  

---

#### 2. Bucle principal
1. Mientras la **pila no esté vacía**, hacer:  
   - `nodo = desapilar(pila)`  
   - `procesar(nodo)`  

- *Desapilar* toma el nodo más reciente, garantizando la exploración en profundidad de la rama actual.  
- *Procesar* realiza alguna acción con el nodo (verificar si es la meta, imprimir su nombre, etc.).  

---

#### 3. Expansión de nodos
1. Para cada **vecino** en `vecinos(nodo)`, hacer:  
   - Si el vecino **no está en visitados**, entonces:  
     - `apilar(vecino)`  
     - `agregar(vecino, visitados)`  

- La verificación evita explorar nodos repetidos.  
- Al añadir el vecino a la pila, se asegura continuar la **búsqueda en profundidad**.  
- El **orden en que se añaden los vecinos** determina qué camino se explora primero.  

---

### Pseudocódigo DFS (Iterativo con pila)

```pseudocode
Funcion DFS(inicio):
    pila ← vacía
    visitados ← conjunto vacío
    
    Apilar(inicio, pila)
    Agregar(inicio, visitados)

    Mientras pila no esté vacía hacer:
        nodo ← Desapilar(pila)
        Procesar(nodo)

        Para cada vecino en vecinos(nodo) hacer:
            Si vecino no está en visitados entonces:
                Apilar(vecino, pila)
                Agregar(vecino, visitados)
            FinSi
        FinPara
    FinMientras
FinFuncion
