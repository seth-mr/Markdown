- *Testing* and *debuggin* are dufferent activities, but debugging must be acoommodated in any testing strategy.

## Software Testing
- La función del Testing es *mostrar que un programa hace lo que es requerido* y para *descubrir defectos en un programa antes de que se ponga en uso.*
	


## El proceso de Testing tiene dos metas distintas:
1. Demostrar al desarrollador y al cliente que el software cumple sus requisitos.
	- *Custom Sofware* ->Debería haber por lo menos un test para cada requerimiento in el documento de requisitos.
	- *Generic software products* -> Debería haber test para todas las características del sistema, y la combinación de estas características que van a ser incorporadas en el lanzamiento del producto.
2. *Descubrir defectos* en que *el software, es incorrecto, no deseable y no esté conforme a la especificación inicial.*

![[Pasted image 20250822073849.png]]
"Testing can only show the presenc of errors, not their abscence." 
-Edsger Dijkstra

- La prueba es una parte más del proceso de verificación y validación del software.
- Barry Boehm, expresa la diferencia entre ellas:
	- *Verificación:* Estamos construyendo el producto correctamente?
	- *Validación:* Estamos construyendo el producto correctamente?

![[Pasted image 20250822074458.png]]

*Casos de prueba:* Son las especificaciones de las entradas del test y la salida esperada del sistema.
*Datos de prueba:* Son las entradas que han sido ingresadas para probar un sistema.

![[Pasted image 20250822082001.png]]


| CP                     | Entradas                        | Salida                       | Resultado      |
| ---------------------- | ------------------------------- | ---------------------------- | -------------- |
| División entre 0       | a = 4 <br>b = 0<br>             | Mensaje de error             | /              |
| Nombre espacios vacios | Nombre: "     "<br>Clic Guardar | Mensaje en cuadro de diálogo | X Si se guardó |
|                        |                                 |                              |                |
## Etapas de testing en un sistema comercial
Un sistema comercial de software va por 3 etapas de testing:
1. *Development testing:* El sistema es probando durante el desarrollo para descubrir bugs y defectos.
2. *Release testing:* Un grupo separado de testers prueban una versión completa del sistema antes que sea lanzada a los usuarios.
3. *User testing:* Donde los usuarios o potenciales usuarios de un sistema prueban el sistema en su propio entorno.


## Actividades de un Ingeniero de pruebas
- Un *Ingeniero de pruebas* es un profesional que está en cargo de una o más actividades de prueba.
	- Design Test Inputs
	- Producing test case values
	- Running test scripts
	- Analyzing results
	- Reporting results to developers and managers.

## Test Manager
- Está a cargo de uno más ingenieros de pruebas
	- Set test policies and processes
	- Interact with other managers on the project
	- Otherwise help the engineers do their work.
	