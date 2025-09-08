Es un *Atributo principal* el swebook ya le hizo su propia área de conocimiento

Se considera una *medida* de capacidad del sistema para *Proteger datos e información* contra el acceso no autorizado, mientras permite el acceso a personas y sistemas autorizadas.




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