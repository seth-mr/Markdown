**Seguridad:** Es una medida de la capacidad del sistema para proteger datos e información contra el acceso no autorizado, mientras permite el acceso a personas y sistemas autorizados.
¿Qué es una táctica de diseño
## Características clásicas: CIA
- *Confidencialidad:* Propiedad que garantiza que los datos o servicios estén protegidos contra el acceso no autorizado.
	- *Objetivo:* Evitar la filtración de información.
	- *Ejemplo:* Cifrado de datos sensibles para protegerlos contra accesos no autorizados
- *Integridad:* Propiedad que garantiza que los datos o servicios no sean manipulados de manera no autorizada.
	- *Objetivo:* Prevenir la modificación o eliminación no autorizada de los datos.
	- *Ejemplo:* Controles de acceso que aseguran que solo usuarios autorizados puedan modificar los registros.
- *Disponibilidad:* Propiedad que garantiza que el sistema esté disponible para el uso legítimo.
	- *Objetivo:* Evitar retrasos significativos o apagados no autorizados.
	- *Ejemplo:* Implementación de redundancia en servidores para prevenir tiempos de inactividad

## Estándar de oro
- *Autenticación:* Es el proceso de verificar que alguien es quien dice ser.
	- *Objetivo:* Asegurar que solo usuarios autorizados puedan acceder al sistema
	- *Ejemplo:* Cuando inicias sesión en un sistema web y te piden tu nombre de usuario y contraseña. El sistema web verifica que la información proporcionada coincide con la que tiene registrada para confirmar tu identidad.
	- Uso de autenticación multifactor (MFA) para verificar la identidad de un usuario. 
- *Autorización:* Es el proceso de asegurarse de que solo las personas correctas puedan hacer ciertas cosas en el sistema.
	- *Objetivo:* Garantizar que solo los usuarios con los permisos adecuados puedan realizar ciertas acciones.
	- *Ejemplo:* Después de iniciar sesión, el sistema verifica qué acciones pueden realizar, como acceder a ciertas funciones, editar archivos o cambiar configuraciones, 
- *Auditoría:* Es el procesos de mantener un registro de todas las acciones realizadas en el sistema por cada usuario.
	- *Objetivo:* Proporcionar un historial de actividades para la detección y prevención de abusos.
	- *Ejemplo:* Un registro de auditoría  puede mostrar quién accedió a un archivo, cuándo lo hizo y qué cambios realizó. Esto ayuda a rastrear actividades y prevenir abusos o identificar problemas.
	- Registros de auditoría que documentan cada intento de acceso y modificación de datos.

**STRIDE:** STRIDE es un modelo de amenazas desarrollado por Praerit Garg y Loren Kohnfelder en Microsoft para la identificación de amenazas de seguridad informática. Cada categoría representa una violación de una propiedad deseable para un sistema, y el acrónimo STRIDE se compone de las siguientes amenazas: Suplantación (Spoofing), Alteración (Tampering), Repudio (Repudiation), Divulgación de Información (Information Disclosure), Denegación de Servicio (Denial of Service, DoS) y Elevación de Privilegios (Elevation of Privilege).

## Ataque
Acción realizadas contra un sistema informático con la intención de causar daño y puede tomar varias formas.
Ejemplos:
- Intento no autorizado de acceder a datos o servicios.
- Intento de modificar datos de forma no autorizada.
- Intento de negar servicios a usuarios legítimos (DoS).

## Superficie de Ataque (Attack Surface)
La totalidad de los puntos de entrada que un atacante podría usar para lanzar un ataque. Un área más amplia expone más puntos vulnerables a potenciales ataques.
Ejemplo:
- El casco de un barco es una superficie de ataque para un torpedo.
- En términos de software, una aplicación con muchas interfaces (APIs) expone una superficie de ataque más grande que  una con menos interfaces.
## Amenaza
Es cualquier circunstancia o evento con potencial de causar daño a un sistema de información o a una organización mediante acceso no autorizado, destrucción, divulgación, modificación o denegación de servicio.
- *Intencionales:* Acciones deliberadas como ataques cibernéticos.
- *Accidentales:* Errores humanos o desastres naturales que pueden comprometer la seguridad de un sistema o la integridad de la información. Threat modeling

## Ejemplos de amenazas
- *Ciberataque:* Un hacker intenta obtener acceso no autorizado a una base de datos para robar información personal.
- *Error Humano:* Un empleado borra accidentalmente archivos importantes

## Categorías de amenazas
- *Spoofing (Suplantación):* Fingir ser algo o alguien que no eres.
- *Tampering (Manipulación):* Modificar algo que no debería modificar.
- *Repudiation (Repudio)* Afirmar que no hiciste algo, independientemente de si lo hiciste o no.
- *Information Disclosure (Divulgación de Inf.)* Exponer información a personas que no están autorizadas para verla.
- *Denial of Service (Denegación de Servicio):* Ataques diseñados para impedir que un sistema proporcione servicio, ya sea bloqueándolo, haciéndolo extremadamente lento o llenando todo su almacenamiento.
- *Elevation of Privilege (Elevación de Privilegios)* Cuando un programa o usuario puede realizar acciones para las que no tiene permiso.


| Objetivo         | Amenaza                                             | Ejemplos                                                                             |
| ---------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Autenticidad     | Spoofing (Suplantación)                             | Phishing, contraseña robada, suplantación de identidad, ataque de repetición.        |
| Integridad       | Tampering (Manipulación)                            | Modificación y eliminación no autorizada de datos, inyección de anuncios (Superfish) |
| No Repudio       | Repudiation (Repudio)                               | Negación plausible, registro insuficiente, destrucción de registros.                 |
| Confidencialidad | Information Disclosure (Divulgación de Información) | Fuga de datos, ataque de canal lateral, cifrado débil, datos en caché residuales     |
| Disponibilidad   | Denial of Service (Negación de Servicio)            | Solicitudes simultáneas inunda un servidor web, ransomware, ataque de "memcrash"     |
| Autorización     | Elevation of Privilege (Elevación de Privilegios)   | Inyección SQL                                                                        |
## Agents (Treat agents) o actores
- Es cualquier individuo o grupo que puede manifestar una amenaza contra los activos de una organización.
- *Importancia:* Identificar quién podría explotar los activos y cómo podrían hacerlo es calve para la seguridad.

## Tipos de agentes
- *No Específicos al Objetivo* Virus informáticos, gusanos, troyanos.
- *Empleados* Personal molesto, contratistas, personal de mantenimiento.
- *Crimen Organizado* Criminales que buscan información valiosa como cuenta bancarias o propiedad intelectual.
- *Corporaciones:* Competidores o socios involucrados en inteligencia competitiva.
- *Humano, no Intencional* Accidentes, descuidos.
- *Humano, Intencional* Insiders malintencionados, atacantes externos.
- *Natural:* Desastres naturales como inundaciones o terremotos.

## Acciones Potenciales de los Agentes
- *Acceso No autorizado* Acceso a activos sin permiso.
- *Uso indebido* Uso de activos para propósitos no autorizados, como robo de identidad.
- *Divulgación* Revelación de información sensible
- *Modificación* Cambios no autorizados en los activos.
- *Denegación de Acceso* Destrucción o robo de activos (assets)

## Impacto de las Acciones de los Agentes
- *Pérdida de Productividad* Depende de la criticidad del activo.
- *Pérdida de Ventaja Competitva* Divulgación de información sensible puede afectar la reputación y generar costos legales.
- *Pérdida de Activos* Robo o destrucción de activos que puede afectar la operación de la organización.

## ¿Y la Privacidad?
- *Definición:* La privacidad es el control que un individuo tiene sobre la recolección, uso y difusión de su información personal.
- *Objetivo:* Proteger la información personal identificable (PLL) y garantizar que solo personas o sistemas autorizados tengan acceso a ella.
- *Relación con la Seguridad* La seguridad ayuda a proteger la privacidad implementando medidas que previenen el acceso no autorizado y aseguran que las personas correctas tengan acceso a la información sensible.

| Seguridad                                                                             | Privacidad                                                             |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Protección de sistemas y datos contra accesos no autorizados                          | Control de uso y difusión de la información personal.                  |
| Se enfoca en la confidencialidad, integridad y disponibilidad de la información (CIA) | Se enfoca en los derechos del individuo sobre su información personal. |
| Ejemplo: Proteger una base de datos contra hackers                                    | Ejemplo: Limitar quién puede ver datos personales en una red social    |

## Modelado de Amenazas.
- *Definición:* Proceso de identifica sistemáticamente las amenazas a un sistema de software para poder registrarlas, rastrearlas y mitigarlas. Implica dibujar un diagrama del sistema, identificar  límites de confianza y considerar amenazas realistas.
- *Objetivo:* Determinar los posibles ataques que pueden comprometer la confidencialidad, integridad o disponibilidad (CIA) de un sistema.
- *Enfoque Proactivo:* Permite a los ingenieros diseñar e implementar medidas para prevenir o mitigar amenazas antes de que ocurran.
## Metodologías de Modelado de Amenazas
- *STRIDE* Identifica amenazas relacionadas con la suplantación de identidad, manipulación, repudio divulgación de información, denegación de servicio y elevación de privilegios.
- *PASTA* Se centra en el análisis de amenazas basado en la perspectiva del atacante y en el impacto del negocio.
- *VAST* Proporciona un enfoque escalable para el modelado de amenazas, adecuado para la automatización y la integración continua.
## Importancia del modelado de Amenazas
- *Identificación de Amenazas* Ayuda a identificar posibles amenazas y debilidades en el sistema.
- *Diseño de Contramedidas:* Permite a los ingenieros diseñar e implementar contramedidas para prevenir o mitigar amenazas.
- *Reducción de Riesgos* Reduce el riesgo de brechas de seguridad y compromisos del sistema.
## Modelos en el Modelado de Amenazas
- *]Definición* Un modelo de sistema es una abstracción o  representación de un sistema diseñado para ser analizado en busca de amenazas.
- *Utilidad* Ayuda a visualizar cómo los cambios en el diseño del sistema pueden afectar su seguridad y facilita la identificación de posibles vulnerabilidades.
	- Diagrama de Flujo de Datos (DFD)
	- Diagramas de Secuncia
	- Diagramas de Flujo de Proceso (PFD)
	- Diagramas de Espina de Pescado (Fishbone)

## Sistema de Gestión de Información Hospitalaria (HIS) Caso de estudio


## Suplantación de Identidad (Spoofing)
- *Amenaza de Suplantación de Usuario* Un atacante podría intentar suplantar la identidad de un médico o un administrativo para acceder a los registros de los pacientes.
	- *Escenario* Un atacante utiliza credenciales robadas de un médico para acceder a registros de pacientes.
- *Manipulación de Datos en Tránsito:* Durante la transferencia de datos entre dispositivos médicos y el HIS, un atacante intercepta y modifica la información, como los resultados de pruebas de laboratorio.
	- *Escenario* Durante la transferencia de datos desde un dispositivo médico al HIS, un atacante intercepta la transmisión y altera los resultados de las pruebas de laboratorio antes de que lleguen al sistema.