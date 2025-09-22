
## Explorando el vecindario

**Idea principal** Las búsquedas locales son una categorismo de algoritmos de optimizacion que buscan la solución a un problema *explorando* solo los estados cercanos al estado actual, sin la necesidad de un grafo o árbol de búsqueda completo

**Analogía** Imagina que estas en un terreno montañoso y tu objetivo es encontrar el punto mas alto. Una búsqueda local es como *caminar* y *siempre subir*, paso a paso. No tienes un mapa completo, solo puedes ver a tu alrededor inmediato u decidir cual es la mejor dirección para subir 

- **Eficiencia en memoria:** Solo necesita recordar el estado actual por lo que lo hace ideal en búsquedas con espacios enormes 

- **Velocidad** Generalmente son muy rápidos ya que no exploran el espacio de búsqueda

- **Óptimos locales** Son susceptibles de quedarse atrapados en un "Optimo loca" que es una solución buena pero no la mejor global-mente

- **No guardan el camino** No te da la secuencia de pasos para llegar a la solucion. 


### HILL CLIMB

Es un algoritmo de búsqueda local que se mueve continuamente en la dirección de  *mejorar el estado actual*, eligiendo al vecino mas provechoso.

Una persona sube una colina y, en cada paso, se mueve en la dirección con la pendiente mas pronunciada. Siempre sube, pero podria terminar en una colina baja en vez de la montaña mas alta.

**Optimalidad** No garantiza encontrar el optimo global

**Simplicidad** Es uno de los algoritmos mas simples de implementar

```Python
función escalador_de_colina(estado_inicial)
    estado_actual ← estado_inicial

    mientras VERDADERO hacer
        vecino_mejor ← encontrar_mejor_vecino(estado_actual)

        si vecino_mejor es mejor que estado_actual entonces
            estado_actual ← vecino_mejor
        sino
            retornar estado_actual
        fin si
    fin mientras
fin función
```




