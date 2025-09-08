Los *atributos de calidad* son las *propiedades medibles* o *verificables* de un sistema que se utilizan para indicar *qué tan bien éste satisface las necesidades* de sus interesados.

- Han sido objeto de estudio por lo menos desde 1970s.
- Existe una gran variedad de taxonomías y definiciones cada uno tienen su propia comunidad de investigación y practicantes.
- Desde la perspectiva de un arquitecto, existen tres problemas con los atributos del sistema.
1. Permiten expresar la calidad de manera objetiva.
2. Evitan la ambigüedad del término "calidad" en su uso informal.
3. Requieren ser *elícitados, especificados, priorizados y validados* adecuadamente.
## Problemas con los atributos de calidad

*Elicitación:*
- Identificar y recopilar los atributos de calidad.
*Especificación:*
- Definir claramente cada atributo con criterios medibles.
*Priorización:*
- Determinar la importancia relativa de cada atributo para guiar el diseño arquitectónico.
*Validación:*
- Verificar que el sistema cumple con los atributos de calidad definidos.

- Existen dos categorías de atributos de calidad:
	- Los que describen una característica de un atributo en *tiempo* de *ejecución*
		- Como disponibilidad, desempeño o usabilidad.
	- Los que describen una *propiedad* del *desarrollo* de sistema.
	- Como modificabilidad o verificabilidad (testability)
- En los sistemas complejos, no se pueden aislar y el alcanzar alguno tiene efectos ( +/-) en otros.

1. Las definiciones proporcionadas por un atributo se pueden probar.
2. La discusión a menudo se centra en el atributo de calidad a la que pertenece una preocupación en particular.
3. Cada comunidad de atributos ha desarrollado su propio vocabulario.

## Relación con la Arquitectura
- Son los factores que más fuertemente moldean la arquitectura.
- Las decisiones durante el diseño arquitectónico determinan en gran parte si el sistema cumplirá o no con los requisitos de calidad.
- La arquitectura es el primer punto en el desarrollo donde se pueden abordar los requisitos de calidad.
*Disponibilidad:* Capacidad de una aplicación o sistema para estar operativo y accesible para los usuarios cuando es necesario, garantizando un mínimo tiempo de inactividad.

## Requisitos relevantes para la arquitectura

- *Requisitos funcionales:* Establecen lo que debe hacer el sistema y cómo debe comportarse o reaccionar a estímulos en tiempo de ejecución.
- *Requisitos de calidad:* Son cualidades de los requisitos funcionales o del producto en general.
- *Restricciones:* Es una decisión de diseño con cero grados de libertad. Es decir, una que ya ha sido tomada.

## Más allá de la funcionalidad
- Las cualidades del sistema incluyen más que solo la funcionalidad.
- La funcionalidad suele recibir más atención en el desarrollo.
- La funcionalidad es la capacidad básica del sistema, pero las *cualidades* abordan *cómo* estas *capacidades* se *implementan y* se *perciben*.
- *Advertencia:* Priorizar solo la funcionalidad es una visión limitada y puede llevar a problemas a largo plazo.

## Problemas comunes
- Los sistemas no se rediseñan por deficiencias funcionales.
- Se rediseñan porque son difíciles de mantener, portar o escalar; son lentos; o han sido comprometidos.
- Falla si no se soporta cualidades como la mantenibilidad, portabilidad o seguridad.

# Algunos atributos de calidad

## Disponibilidad
- La capacidad de un sistema para estar disponible y listo para realizar su tarea cuando se necesita.
- Incluye la capacidad de recuperación tras una falla.
- Relacionado con la fiabilidad, robustez y otros atributos de calidad.
- *Importancia:* Asegura que el tiempo de inactividad no exceda un valor requerido en un intervalo de tiempo especificado.
- *Falla (failure):* Desviación del sistema respecto a su especificación, que es visible externamente es el resultado final de un error en el sistema.
- *Defecto (fault):* La causa de una falla. Puede ser un defecto en el código, diseño, o en el proceso.
- *Error:* Acción incorrecta realizada por un desarrollador o usuario que introduce un defecto en el sistema.
- *Resiliencia:* Capacidad del sistema para prevenir, tolerar, eliminar o anticiparse a defectos para evitar que se conviertan en fallas.


## Disponibilidad y otros atributos
- *Disponibilidad y Seguridad:*
	- Una ataque de denegación de servicio (DoS) buscan hacer que un sistema  no esté disponible.
- *Disponibilidad y Rendimiento:*
	- Un sistema lento puede confundirse con un sistema que ha presentado una falla.
- *Disponibilidad y Protección:*
	- Evita que el sistema entre en un estado peligroso y limita el daño en caso de fallas.

*Comprensión de las fallas:*
	- ***Desafió Principal:*** Identificar y entender la naturalidad de las fallas que pueden surgir durante la operación del sistema.
	- ***Importancia*** una vez comprendidas, se pueden diseñar estrategias de mitigación efectivas.
*Mitigación de fallas:*
	- Diseñar el sistema para minimizar el impacto de las fallas y reducir el tiempo


*Observabilidad de la Falla:*
- *Definición:* Una falla es observable cuando es perceptible por los usuarios, ya sea a través de un retraso o una interrupción más significativa.
- *Tiempo de Reparación:* El tiempo necesario para que la falla deje de ser observable por los usuarios.
- *Ejemplo Extremo:* El tiempo que toma enviar a alguien a reparar una máquina en una ubicación remota.
- *Modo degradado:* Nivel de capacidad que queda cuando se produce una falla.

## Gestión de fallas
1. *Prevención:* Evitar la introducción de defectos en el sistema.
2. *Tolerancia:* Diseñar el sistema para que continúe operando correctamente incluso si se produce una falla.
3. *Eliminación:* Detectar y corregir defectos para evitar que causen fallas.
4. *Predicción:* Anticipar la aparición de fallas y tomar medidas preventivas.
- *Resiliencia:* Un sistema se vuelve resiliente al manejar adecuadamente las fallas a través de las acciones mencionadas.

## Medición de la Disponibilidad
- La probabilidad de que el sistema proporcione los servicios especificados dentro de los límites requeridos durante un intervalo de tiempo determinado.

*Fórmula para Calcular la Disponibilidad:*
	Disponibilidad = MTBF / (MTBF + MTTR)
		Falla = 1 - Disponibilidad
- *MTBF( Tiempo medido Entre Fallas)* Promedio de tiempo que el sistema opera sin fallar.
- *MTTR(Tiempo Medio de Reparación)* Promedio de tiempo necesario para reparar el sistema tras una falla.

*Interpretación en Software:*
- *MTBF:* Evalúa qué factores podrían causar la falla de un sistema y con qué frecuencia pueden ocurrir.
- *MTTR:* Considera cuánto tiempo se necesitará para reparar el sistema después de una falla.
- *Importancia:* Esta fórmula es fundamental para cuantificar la disponibilidad y planear estrategias de mantenimiento y recuperación.

## MTBF (Tiempo Medio Entre Fallas)
- Este valor se calcula dividiendo el tiempo de operación del sistema entre el número total de fallas ocurridas durante ese tiempo.
- *Ejemplo:* Si un servidor ha funcionado 10,000horas y ha fallado 5 veces, su MTBF es de 2,000 horas.

![[Pasted image 20250821121815.png]]

## MTTR (Tiempo Medio de Reparación)
- Se calcula dividiendo el tiempo total dedicado a reparar fallas entre el número de fallas reparadas.
- *Ejemplo:* Si se han dedicado 10 horas parar reparar 5 fallas, el MTTR sería de 2 horas.
	- A partir de la fórmula D = MTBF / (MTBF + MTTR)  es posible calcular la disponibilidad del sistema.
	- *Ejemplo:*
		- El sistema tiene una disponibilidad del 99.999% o
		- Hay una probabilidad del 00.001 de no lo esté

## Tiempos de Inactividad Programados
- *Definición:* Periodos en los que el sistema se detiene intencionalmente de servicio.
- *Impacto en la Disponibilidad:* Los tiempos de inactividad programados no se consideran en el cálculo de la disponibilidad, ya que se asume que el sistema "no es necesario" durante estos procesos.

## Service Level Aggreement (SLA)
- *Definición:* Un SLA específica el nivel de disponibilidad garantizado por el proveedor de un servicio.
- También suele incluir las penalizaciones aplicaciones si no se cumple el nivel de servicio acordado.
*Ejemplo de SLA - Amazon EC2:*
- *Compromiso de Servicio:* Amazon se compromete a mantener un porcentaje de tiempo de actividad mensual de al menos 99.99% en cada región de AWS.
- *Compensación:* Si los servicios incluidos no cumplen con el compromiso de servicio, los clientes son elegibles para recibir un crédito de servicio.

## Alta Disponibilidad
- Se refiere a diseños que apuntan a una disponibilidad del 99.999% o superior (conocido como "5 nueves").
- Solo las interrupciones no programadas se consideran en el cálculo del tiempo de inactividad del sistema.

*Requisitos de Disponibilidad:*
- Los SLA suelen especificar los requisitos de disponibilidad, incluyendo valores umbrales aceptables para el tiempo de inactividad medido en periodos de observación de 90 días o  un año.

| Availability | Downtime / 90 Days | Downtime / year  |
| ------------ | ------------------ | ---------------- |
| 99.0         | 21 hr, 36 min      | 3 days, 15.6 hrs |

## Actividad Cálculo de Disponibilidad
- Gestionas un servidor de bases de datos críticas en un centro de datos.
- El sistema ha operado un total de 100,000 horas. 
- En ese tiempo se han registrado 10 fallas y se ha dedicado 20 horas a reparaciones
- Calcule la disponibilidad del sistema.
D = MTBF / (MTBF + MTTR)
100,000 / 10

10,000 / (10,000  + 2)
10,000 / 10,002
0.9998000399920016

- *Escenario 2*