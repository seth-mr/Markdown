
***los atributos de calidad son propiedades medibles o verificables que utilizan para indicar que tan bien este satisface las necesidades de sus interesados.***

- estos han sido objeto de estudio por lo menos desde los 1970
- Existe una gran variedad de **taxonomias** y definiciones, cada uno tiene su propia comunidad de investigación y practicantes
- Permiten expresar la **calidad de manera objetiva**
- Evitan la ambiguedad de termino "calidad" en su uso informal 
- Requieren ser **elicitados, especificados, priorizados y validados**



**2 tipos
**
- *En tiempo de ejecucion.*
- *Propiedad del desarrollo.*




# Disponibilidad 

- Capacidad del sistema para estar disponible y **listo cuando se necesita**
- Incluye la capacidad de **recuperarse tras una [[falla]]**
- *Relacionado* con la fiabilidad, robustez y otros atributos de calidad
- *Importancia* Asegura que el tiempo de inactividad no exceda un valor requerido en un intervalo de tiempo especificado.

 *[[FALLA]]* ->
	Desviación del sistema respecto a su especificación, que es visible externamente es el resultado final de un error en el sistema. 

*DEFECTO* ->
	La causa de una [[falla]]. Puede ser un defecto en el codigo, [[diseño]], o en el proceso.

*ERROR* ->
	Accion incorrecta realizada por un desarrollador o usuario que introduce un defecto en el sistema.

*RESILIENCIA* ->
	Capacidad del sistema para prevenir, tolerar, eliminar o anticiparse a defectos para evitar que se convierten en fallas.


| Disponibilidad y seguridad   | un ataque de denegacion                           |
| ---------------------------- | ------------------------------------------------- |
| Disponibilidad y rendimiento | un dia lento puede confundirse con una [[falla]]      |
| disponibilidad y proteccion  | evita que el sistema entre en un estado peligroso |
#### Medicion de la disponibilidad

*FORMULA PARA CALCULAR LA DISPONIBILIDAD*

*Tiempo de Inactividad Programado*
Tiempo en el que el sistema detiene intencionalmente el servicio.

Esta formula es fudnamental para cuantificar la disponibilidad y planear estrategias de mantenimiento y recuperacion , es necesario recalcar que los tiempos en el que el sistema esta *incativo* por decision *propia no son considerados en el calculo*

***DISPONIBILIDAD = MTBF /(MTBF + MTTR)***

[[FALLA]] = 1- DISPONIBILIDAD

*MTBF*
- Tiempo medio entre fallas
- Evalúa que factores podrian causar fallas en el sistema y con que frecuencia pueden ocurrir

*MTTR* 
- Tiempo medio de reparacion 
-  Considera cuanto tiempo se necesita para recuperar el sistma despues de una [[falla]]

### Service Level Aggreement (SLA)
- Definición: Un SLA específica el nivel de disponibilidad garantizado por el proveedor de un servicio.
- También suele incluir las penalizaciones aplicaciones si no se cumple el nivel de servicio acordado.
Ejemplo de SLA - Amazon EC2:
- Compromiso de Servicio: Amazon se compromete a mantener un porcentaje de tiempo de actividad mensual de al menos 99.99% en cada región de AWS.
- Compensación: Si los servicios incluidos no cumplen con el compromiso de servicio, los clientes son elegibles para recibir un crédito de servicio.

#### ALTA DISPONIBILIDAD

Se refiere a diseños que apuntan a una disponibilidad de 99.999% o superior
solo las interrupciones no programadas se consideran en el calculo de inactividad en el sistema.

Los *SLA* suelen especificar los requisitos de disponibilidad, incluyendo valores umbrales aceptables para el tiempo de inactividad medio en periodos de observacional de 90 dias o un año 

---
## Problemas

*ELICITACION* ->
	identificar y recopilar los atributos de calidad.
*ESPECIFICACION* -> 
- Definir claramente cada atributo como criterio medible.
*PRIORIZACION* -> 
- Determinar la importancia relativa de cada atributo para guiar el [[diseño]] arquitectonico
*VALIDACION* -> 
- Verificar que el sistema cumple con los atributos de calidad definidos

Existen dos ***categorias de atributos de calidad***

los que describen una caracteristica en *tiempo de ejecucion*
- Disponibilidad
- Desempeño
- Usabilidad

los que describen una *propiedad del desarrollo*
- modificabilidad
- verificabilidad

## RELACION CON LA ARQUITECTURA

Son los factores que mas fuertemente **modifican la arquitectura**

Las decisiones durante el [[diseño]] arquitectonico **determinan** en gran parte si el sistema  **cumplira** o no con los requisitos de **calidad.**

La arquitectura es el ***primer punto en el desarrollo donde se pueden abprdar los requisitos de calidad***


*Requisitos funcionales:* -> 
- Establecen lo que debe ser el sistema y como debe comportarse o reaccionar a estimulos en tiempo de ejecucion 

*Requisitos de calidad:* ->
- Son cualidades de los requisitos funcionales o del producto general.

*Restricciones :* -> 
- Es una decision de [[diseño]] con cero grados de libertad. Es decir, una que ya ah sido tomada


# USABILIDAD

- Se refiere a que *tan fácil* es para el usuario *completar una tarea*
- También se enfoca en el tipo de *soporte* que el *sistema proporciona* al usuario

**IMPORTANCIA** 

- Es una de las formas *mas económicas* y *fáciles* de mejorar un sistema
- Mejora la percepción del usuario sobre la calidad del sistema y aumenta la perfecciones positiva

## ÁREAS DE USABILIDAD

**Aprendizaje de funcionalidades** 

- Facilita que el usuario aprenda a utilizar el sistema, cuando no esta familiarizado con el o una parte de el. Por ejemplo, con funciones de ayuda.

**Uso Eficiente del sistema** 

- Lo que hace el sistema para mejorar la eficiencia del usuario. Por ejemplo, el usuario puede suspender una tarea , desarrollar varias operaciones simultáneamente o continuar con una tarea.

**Minimizar el impacto de los errores** 

- Reducir el impacto de los errores del usuario mediante opciones para cancelar o deshacer opciones.

**Adaptación de las necesidades de uso** 

- Personalizar el sistema para facilitar tareas del usuario, como auto completar.

**Aumento de confianza y satisfacción** 

- Proporciona retroalimentación que indique el progresa de tareas, aumentando la confianza del usuario. 

## INICIATIVA DEL USUARIO Y DEL SISTEMA

### INICIATIVA DEL USUARIO

- El usuario toma la iniciativa de realizar acciones especificas y como procede la intereaccion como cancelar un comando 

### INICIATIVA DEL SISTEMA
- El sistema toma la iniciativa para realizar acciones o proporcionar informacion como mostrar el indicador de proceso durante una operacion.

### INICIATIVA MIXTA
- Combinación de ambas iniciativas para mejorar la interacción, como durante una cancelación donde el cliente inicia la acción pero el sistema proporciona retroalimentación

## RELACIÓN  USABILIDAD Y MODIFICABILIDAD

**Iteracion en el [[Diseño]] de interfaz.** 

- El [[diseño]] de la *interfaz de usuario es un proceso iterativo* que requiere ajustes y mejoras constantes.
- Es improbable que se obtenga un [[diseño]] perfecto en el primer intento.

La capacidad de mejorar el sistema facilmente facilita la mejora continua de usabilidad.


## PATRONES DE USABILIDAD

- Se han desarrollado para *Apoyar el [[diseño]] de UI*, enfocándose en la facilidad de modificación para mejorar la usabilidad.
- Promueven la *Separacion de responsabilidades* para facilitar la interacción del [[diseño]] de interfaces de usuario 
- *Modificar* el sistema *repetidamente*, basándose en el aprendizaje del comportamiento y las necesidades del usuario, es *clave* lograr *alta usabilidad*

### MVC

**Beneficios**
- Facilita [[cambios]] en la UI sin afectar la logica del sistema.
- Permite el desarrollo y [[pruebas]] paralelas de cada componente.
- Un modelo puede usarse con diferentes vistas, y viceversa.

**Tradeoffs**
 - Puede ser *complicado para UIS complejas*
 - Añade complejidad inicial que puede no ser necesaria para las UIs simples.
 - Introduce una pequeña latencia en la interacción del usuario 

### OBSERVER

se puede usar para vincular funcionalidades con una o mas vistas, Consiste en una entidad observadora y uno o mas observadores que se registran para recibir notificaciones de [[cambios]] de estado en el sujeto.

**Beneficios**
- Separan funcionalidades
- Flexibilidad en Tiempo de Ejecución. permite cambiar los vínculos entre el sujeto y los observadores durante la ejecucion 

**Compromisos**
- Complejo para múltiples vistas 
	- Puede ser innecesario si no se requieren múltiples vistas
- Problemas de registro
	- Los observadores deben registrarse y cancelar su registro; no hacerlo puede causar fugas de memoria y afectar el rendimiento.
- Procedimiento innecesario 
	- Los observadores pueden necesitar procesar cada cambio de estado, incluso si no todos los [[cambios]] son relevantes.

### Memento
Permite implementar la función de deshacer(undo ) en un sistema.

**Partes**

- *Originador* Procesa eventos que cambian su estado.
- *Cuidador* Envía eventos al originador que modifican su estado y puede solicitar un memento para guardar el estado actual.
- *Memento* Una instancia del estado actual.

**Beneficios**
- Se delega el complicado proceso de implementar la funcion de deshacer y determinar que estado conservar a la clase que realmente crea y administra ese estado.
- Se conserva la abstraccion del creador y el resto del sistema no necesita verlo

**Compromisos**
- El memento puede consumir mucha memoria, dependiendo del tamaño del estado que se guarda lo cual puede afectar al rendimiento.
- Complejidad en algunos lengiajes, puesto que puede ser complicado manejar como se guarda y restaura el estado de forma eficiente.

## Escenarios de atributos de calidad.

Existe un escenario general por cada atributo de calidad y varios escenarios concretos para el sistema que se esta diseñando.

- Se pueden verificar y no son ambiguos
- Se pueden expresar con los siguientes componentes
	- Estímulo
		- Usabilidad -> Llevar a cabo una tarea
	- Artefacto
		- Seguridad -> En inyección de código el artefacto es la base de datos
- Los escenarios son la forma en la que se pueden expresar los requisitos de atributos de calidad
### Elementos del escenario general
- *Estímulo:* Es una condición que requiere una respuesta cuando llega al sistema
- *Fuente del estímulo:* Es una entidad que generó el estímulo
- *Ambiente:* El evento ocurre en ciertas condiciones. Es el estado en que se encuentra el sistema
- *Artefacto:* El sistema o parte de el que es estimulada
- *Respuesta:* Es la actividad emprendida como resultado de la llegada del estímulo
- *Medida de la respuesta:* Cuando ocurre la respuesta, se debe medir de alguna forma para que el requisito se pueda verificar
- Existe un escenario general por atributo de calidad y varios escenarios concretos para el sistema que se está diseñando
	- Sigue siendo una abstracción pero ya es más específico


### Priorizar escenarios de QA
Antes de comenzar el diseño, prioriza tus escenarios de atributos de calidad
Típicamente solo los escenarios más importantes pueden ser considerados al inicio del diseño arquitectónico
Elige los 5-7 escenarios principales en la primera ronda de diseño
Existen dos estrategias principales para recopilar escenarios de AC: Taller de atributos de Calidad (QAW, pro sus siglas en inglés) y Árbol de utilidad


# SEGURIDAD

Es un *Atributo principal* el swebook ya le hizo su propia area de conocimiento

Se considera una *medida* de capacidad del sistema para *Proteger datos e informacion* contra el acceso no autorizado, mientras permite el acceso a personas y sistemas autorizadas.




## CARACTERÍSTICAS CLASICAS: CIA



|   **Caracteristica**   | Definicion                                                                                            | Objetivo                                                                           |     | Ejemplo                                                                                                            |
|:----------------------:| ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------ |
| ***Confidencialidad*** | Propiedad que garantiza que los datos o servicios estén protegidos contra el acceso no autorizado.    | Evitar filtraciones                                                                |     | Cifrado de datos sensibles para protegerlos contra accesos no autorizados.                                         |
|    ***Integridad***    | Propiedad que garantiza que los datos o servicios no sean manipulados de manera no autorizada.        | Prevenir que las modificación o eliminación no autorizada de datos                 |     | Controles de acceso que aseguran que soautprozadoslo usuarios autorizados puedan modificar los registros           |
|  ***Disponibilidad***  | Propiedad que garantiza que el sistema este disponible para el uso legitimo                           | Evitar retrasos significativos o apagados no autorizados                           |     | Servidores redundantes para no sufrir                                                                              |
|  ***Autenticacion***   | Asegurarse de que alguien es quien dice ser                                                           | Asegurar que solo los usuarios autorizados puedan acceder al sistema<br>           |     | Cuando inicias sesión en un sistema web y te piden usuario y contraseña o un factor de verificación múltiple .<br> |
|   ***Autorización***   | Es el proceso de asegurar que solo las personas correctas puedan hacer ciertas cosas en el sistema.   | Garantizar que solo los usuarios con los permisos pueden realizar ciertas acciones |     | Después de iniciar sesión el sistema verifica que acciones puedes realizar.                                        |
|    ***Auditoria***     | Es el proceso de mantener un registro de todas las acciones realizadas en el sistema por cada usuario | Proporcionar un historial de actividades para la detección y prevención de abusos. |     | Un registro de auditoria de todos los retiros que aprueba un cajero del banco prevención                           |



## ATAQUE 

Accion realizada contra un sistema informático *con la intención de causar daño*

**Ejemplos**

- Intento de acceso no autorizado
- intento de modicicacion de datos no autorizados
- intento de negar servicios a usuarios legítimos


## SUPERFICIE DE ATAQUE 

Totalidad de los *puntos de entrada* que una atacante podria usar para lanzar un ataque. Un area mas amplia expone mas puntos vulnerables a potenciales ataques.

**Ejemplos**

- El casco de un barco es una superficie de ataque para un torpedo
- En términos de software si se tienen muchas interfaces publicas o muchos puertos abiertos se tiene mas superficie de ataque.


## AMENAZA

Es cualquier circunstancia o evento con *potencial de causar daño a un sistema* de informacion o a una organización mediante acceso no autorizado, destrucción, divulgación, modificación o denegación de servicio

**Intencionales** Acciones deliberadas como ataques ciberneticos

**Accidentales** Errores humanos o desastres naturales que pueden comprometer la seguridad del sistema o la integridad de la situación 

**Ejemplos**

- Ciberataques
- Errores Humanos
- Desastres naturales Ciberataques



### Categorías de amenazas


|          Amenaza           | Que es                                                                                                           | Que ataca |
|:--------------------------:| ---------------------------------------------------------------------------------------------------------------- |:---------:|
|        **Spoofing**        | Fingir ser algo o alguien que no se es                                                                           |           |
|       **Tampering**        | Modificar algo que no se debería modificar                                                                       |           |
|      **Repudiation**       | Afirmar que no hiciste algo, independientemente de si lo hiciste o no                                            |           |
| **Information Disclosure** | Exponer informacion que no están autorizadas para verla                                                          |           |
|   **Denial of service**    | Ataques diseñados para impedir que un sistema proporcione un servicio ya sea bloqueándolo o haciéndolo muy lento |           |
| **Elevation of provilege** | Cuando un usuario o app puede realizar acciones para las que no tiene permiso                                    |           |



### Agentes

#### Tipos de agentes

- **No específicos** Virus, gusanos, troyanos
- **Empleados** Personal molesto, contratistas, mantenimiento
- **Crimen Organizado** Criminales que buscan informacion valioso como cuentas bancarias
- **Corporaciones** Competidores
- **Natural** Desastres naturales
- **Humano, intencional** Insidies maliciosos
- **Humano, no intencional** Accidentes, descuidos.

#### Acciones potenciales

- **Acceso no autorizado** Acceso a activos sin permiso
- **Uso indebido** Uso de activos para propósitos no autorizados.
- **Divulgación** Revelación de informacion sensible
- **Modificación** Cambios no autorizados en los activos
- **Denegación** Destrucción o robo de activos

#### Impacto de las acciones de los agentes

- **Perdida de productividad** Depende de la criticidad del activo 
- **Perdida de ventaja competitiva** Divulgación de informacion sensible para afectar la reputación y generar costes
- **Perdida de activos**

### Privacidad

- **Definición** 
	- Es el control que un individual tiene sobre la recoleccion uso y difusion de su informacion personal

- **Objetivo** 
	- Proteger la informacion personal identificable y garantizar que solo personas o sistemas autorizados tengan acceso a ella

- **Relación con la seguridad**
	- La seguridad ayuda a proteger la privacidad implementando medidas que previenen el acceso no autorizado y aseguran que solo las personas correctas tengan acceso a la informacion sensible


| Proteccion de sistemas y datos contra accesos no autorizados                    | Control de uso y difusion de la informacion personal                  |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Se enfoca en la confidencialidad, integridad y disponibilidad de la informacion | Se enfoca en los derechos del individuo sobre su informacion personal |
| Ejemplo: Proteger una base de datos contra los hackers                          | Ejempplo: Limitar quien puede ver datos personales en la red social   |

### Modelado de amenaza

- **Definición** 
	- Proceso de identificar sistemáticamente las amenazas a un sistema de software para poder registrarlas y mitigarlas. Implica dibujar un diagrama del sistema, identificar limites de confianza y considerar amenazas realistas
	
- **Objetivo**
	- Determinar los posibles ataques que puedes comprometer la confidencialidad, integrado disponibilidad
	- Diseñar contramedidas
	- Reducir riesgos
	¡
- **Enfoque Proactivo**
	- Permite a los ingenieros diseñar e implementar medidas para prevenir o mitigar amenazas antes de que ocurran


**Stride** Identificar amenazas relacionadas con la suplantación de identidad,manipulacion,repudio,divulgación,denegación y elevación

**Pasta** Se centra en en análisis de amenazas basado en la perspectiva del atacante y el impacto del negocio

**VAST** Proporcionar un enfoque escalable para el modelado de amenazas, adecuado para la automatización y la integración con

#### Modelos

Un modelo de sistema es una abstracción o representación de un sistema diseñado para ser analizado en busca de amenazas

- **Diagrama de flujo de datos**
- **Diagrama de Secuencia**
- **Diagrama de flujo de procesos**
- **Diagrama de espina de pescado**


