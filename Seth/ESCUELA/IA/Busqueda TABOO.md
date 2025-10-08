Es una metaheuristica que mejora la búsqueda local añadiendo una "memoria" Mantiene una *lista de los ultimos estados visitados* (taboo)

**Analogía**
- Un explorador en un laberinto lleva un registro de los últimos 5 cruces que ah tomado para evitar volver a ellos de inmediato

**Robustez**  
- Al evitar ciclos, puede escapar de óptimos locales al explorar áreas del espacio de búsqueda de otro modo ignoraría

**Complejidad**
- Requiere mas memoria que el escalado de colina debido a la lista taboo }

el algoritmo va a utilizar una lista que almacena los estados recientes para optimizar la busqueda.

```python
Funcion BusquedaTabu(estado_inicial, tamaño_lista_tabu)
    estado_actual ← estado_inicial
    mejor_solucion ← estado_actual
    lista_tabu ← [estado_inicial]

    Mientras NO se cumple criterio_de_parada hacer
        vecinos ← GenerarVecinos(estado_actual)
        vecinos_validos ← FiltrarVecinos(vecinos, lista_tabu)

        mejor_vecino ← SeleccionarMejor(vecinos_validos)

        estado_actual ← mejor_vecino

        Si mejor_vecino es mejor que mejor_solucion entonces
            mejor_solucion ← mejor_vecino
        Fin Si

        Agregar(estado_actual, lista_tabu)

        Si tamaño(lista_tabu) > tamaño_lista_tabu entonces
            EliminarMasAntiguo(lista_tabu)
        Fin Si
    Fin Mientras

    Retornar mejor_solucion
Fin Funcion

