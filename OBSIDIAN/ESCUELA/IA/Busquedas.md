
**¿Que es?**

En la IA, La *Búsqueda* es un proceso fundamental para resolver problemas, y consiste en *explorar un espacio de posibles soluciones* para encontrar lo mejor o mas adecuado para un problema dado siendo así; se utiliza cuando no existe un método directo para llegar a la solución y se necesita *recorrer diferentes caminos*.

**Elementos clave**

Todo problema de busqueda se define por
- Estado inicial 
- Acciones
- Estados sucesores
- Estados meta


**Ejemplos**

- Encontrar la *ruta mas corta* en una aplicación de mapas.
- Resolver *Rompecabezas* como el rubik
- Planificar *Movimientos ooptimos* en un juego de ajedrez 

## Tipos de búsqueda

|      TIPO      | Busqueda no informada                                                                                                                                                                   |                                                                                         Busqueda informada                                                                                         |     |
| :------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | --- |
|  **Problema**  | ir de la casa a la univerciad                                                                                                                                                           |                                                                                   Ir de la casa a la univercidad                                                                                   |     |
| **Estrategia** | Probar todas las rutas                                                                                                                                                                  |                                                                           Usar informacion para tomar la mejor decision                                                                            |     |
|   **Metodo**   | Explorar todas las calles hasta dar con la uni                                                                                                                                          |                                                                         Elegir la ruta que parece mas corta en cada cruce                                                                          |     |
| **Resultado**  | Tarde o temprano voy a llegar                                                                                                                                                           |                                                                              Es muy probable que llegues mas rapido.                                                                               |     |
|  **General**   | No utilizan conocimientos adicionales<br>- Exploran el espacio de estados de manera sistematica<br>- BFS busqueda de amplitud<br>- DFS busqueda en profundidad<br>- Busqueda exhaustiva | Usan unformacion extra (Heuristicas)<br>- la heuristica es una funcion que estima la cercania a la meta<br>- Usar mapas para elegir la ruta mas corta<br>- Greedy<br>- A*<br>- Ramificacion y poda |     |
|                |                                                                                                                                                                                         |                                                                                                                                                                                                    |     |
## Criterios de evaluación

- **Completitud** ¿El algoritmo siempre encuentra una solución si esta existe?
- **Optimalidad** ¿El algoritmo garantiza encontrar la mejor solución si esta existe ?
- **Complejidad en tiempo** ¿Cuanto tiempo tarda en ejecutarse el algoritmo(numero de pasos)?
- **Complejidad en espacio** ¿Cuanta memoria o espacio de almacenamiento necesita el algoritmo?



