 
 Desviación del sistema respecto a su especificación, que es visible externamente es el resultado final de un error en el sistema. 

*Desafio principal* Identificar y entender la naturalidad de las fallas que pueden surgir durante la operacion del sistema

*Importancia* una vez, comprendidas, se pueden diseñar estratefias de mitigacion efectivas.

*Mitigacion de fallas* Diseñar el sistema para minimizar el impacto de las fallas y reducir el tiempo.

### OBSERVABILIDAD DE LA FALLA

- *Definición* una falla es observable y perceptible por parte de los usuario
- *Tiempo de reparación* El tiempo necesario para que la falla deje de ser observable por los usuarios
- *Modo degradado* Nivel de capacidad que queda cuando se produce una fa

### GESTION DE FALLAS 

1. *Prevencion*: Evita la introduccion de defectos en el sistema
2. *Tolerancia*: Diseñar el sistema para que continue la operacion correctamente incluso si se produce una falla
3. *Eliminacion*: Detectar y corregir defectos para evitar que causen fallas
4. *Prediccion*: Anticipar la aparicion de las fallas y tomar medidas preventivas

### Medicion de la disponibilidad

[[Seth/ESCUELA/Diseño de Software/ATRIBUTOS DE CALIDAD]]

*FORMULA PARA CALCULAR LA DISPONIBILIDAD*
Esta formula es fudnamental para cuantificar la disponibilidad y planear estrategias de mantenimiento y recuperacion 

***DISPONIBILIDAD = MTBF /(MTBF + MTTR)***

FALLA = 1- DISPONIBILIDAD

*MTBF*
- Tiempo medio entre fallas
- Evalúa que factores podrian causar fallas en el sistema y con que frecuencia pueden ocurrir

*MTTR* 
- Tiempo medio de reparacion 
-  Considera cuanto tiempo se necesita para recuperar el sistema despues de una falla
