Los *Atributos de calidad* son las propiedades medibles o comprobables.
1. Las definiciones proporcionadas para un atributo no se pueden probar (verificar)
2. La discusión a menudo se centra en el atributo de calidad a la que pertenece una preocupación en particular.
3. Cada comunidad

## ¿Por qué cambia el software?
- *Funcionales:* Adición, eliminación o modificación en las funcionalidades que el sistema ofrece.
- *Tecnológicos:* Adaptaciones a nuevas plataformas o tecnologías.
- *Regulatorios:* Ajustes para cumplir con nuevas normativas.
- *Mantenimiento:* Corrección de errores y mejoras en la eficiencia.
- *Capacidad y Escalabilidad:* Cambios para soportar más usuarios o aumentar las capacidades dle sistema
## Ejemplos
- *Funcionales:* Añadir una nueva funcionalidad de búsqueda avanzada en una aplicación de comercio electrónico.
- *Regulatorios:* Actualización de un sistema de gestión gubernamental para cumplir con los nuevos requisitos de protección de datos según la GDPR.
	- Incluye la implementación de mecanismos de cifrado de datos y cambios en la forma en que los datos son almacenados y accedidos.
- *Mantenimiento:* Optimización de un sistema de gestión de inventario para mejorar la eficiencia de las consultas de bases de datos.
	- Implica la reescritura 
- *Capacidad y Escalabilidad:* Escalar una aplicación web para manejar 10 veces más tráfico durante un evento de ventas masivas.
	- Implica 

## Factores del cambio en el software
- Que puede cambiar
- Probabilidad de cambio
- *Cuándo y quién realiza el cambio:* Cambios pueden ocurrir en cualquier fase (implementación, compilación, configuración y ejecución) y pueden ser realizados por desarrolladores, usuarios finales, administradores del sistema o incluso el sistema mismo.
- *Costo del cambio:* Involucra los recursos para implementar mecanismos para facilitar cambios y los recursos necesarios para realizar cambios usando esos mecanismos.

## ¿Qué puede cambiar?
*Cualquier aspecto de un sistema:*
- Las *funciones* que el sistema realiza.
- La *plataforma:* el hardware, el sistema operativo, el middleware.
- El *entorno* en el que opera: Los sistemas con los que debe interoperar, los protocolos que utiliza para comunicarse con el resto del mundo.
- Las *cualidades* del sistema: Su  desempeño, confiabilidad, futuras modificaciones y capacidad (número de usuarios soportados y de operaciones simultáneas).

## ¿Cuál es la probabilidad de cambio?
- *No* es posible diseñar para *todos* los cambios potenciales pues en inviable.
- *Altos costos*: Incrementa significativamente el costo del desarrollo.
- *Problemas de calidad:* Podría comprometer otras dimensiones como rendimiento o seguridad.
- Priorizar cambios probables: Enfocarse en los cambios más probables durante el ciclo de vida.

## ¿Cuándo se realizan los cambios?
- *En la implementación:* Modificación directa del código fuente.
- *Durante la compilación:* Uso de switches de compilación para adaptar el comportamiento.
- *Durante la construcción:* Selección de bibliotecas específicas para la construcción del sistema.
- *En la configuración:* Ajustes durante la configuración

## ¿Quién realiza los cambios?
- *Desarrolladores:* Realizan los cambios en el código y estructura del software-
- *Usuarios finales* Pueden realizar ajustes menores, como cambiar el protector de pantalla.
- *Administradores de sistemas:* Gestionan cambios en la configuración y despliegue del software.
- *Sistemas auto-adaptativos:* El software se ajusta automáticamente en respuesta al entorno.

## El costo del cambio
*Dos tipos de Costos Involucrados*
- *Introducción del Mecanismo:* El costo asociado con la implementación de mecanismos que faciliten futuros cambios.
- *Realización de la Modificación:* El costo asociado con realizar un cambio utilizando los mecanismos introducidos.
- Si un sistema tiene una arquitectura rígida sin mecanismos de modificabilidad, cualquier cambio puede requerir modificaciones extensas en múltiples áreas del código.
- Esto 

## Cambio Simple
- *Mecanismo*
	- Cambiar el código fuente directamente tras recibir una solicitud de cambio.
- *Costos:*
	- *Introducción:* Ninguno, ya que no se introduce un mecanismo especial.
	- *Realización.* Costo de modificar el código y revalidar el sistema.

## Generador de Aplicaciones (Ej. Constructores de Interfaces)
- *Mecanismo:*
	- Uso de herramientas que generan código basado en la descripción de la UI.
- *Costos:*
	- *Introducción:* Alto, debido a la adquisición de la herramienta.
	- *Realización:* Puede 

## Sistemas Auto-Adaptativos
- *Mecanismos:*
	- Sistemas que detectan su entorno, aprenden y se modifican automáticamente.
- *Costos:*
	- *Introducción:* Alto, debido a la implementación y pruebas de mecanismos de aprendizaje.
	- *Realización:* Casi nulo, ya que el sistema se modifica automáticamente.

## Justificación del Mecanismo
- *Considerar el costo de oportunidad* Los recursos podrían destinarse a mejorar otras áreas.
- *Evaluar el impacto temporal:* A veces es mejor un mecanismo a largo plazo, pero los plazos pueden limitar esta opción.
- *Evitar deuda técnica:* Cambios continuos sin un mecanismo adecuado pueden acumular deuda técnica.

## Deuda técnica
- *Elementos* (decisiones de diseño o implementación que son convenientes en el corto plazo pero que crean un contexto técnico que puede hacer que un cambio futuro sea más costoso o imposible.)
- Limita las cualidades internas: mantenibilidad y la facilidad de evolución.
- Introduce complejidades adicionales y obstáculos que dificultan la implementación de cambios futuros.
- Existen diferentes tipos de Deuda técnica.

## Ejemplos de Deuda técnica
- Parche Rápido para corrección de errores.
- Uso de bibliotecas o frameworks obsoletos.
- Código duplicado en varias partes del sistema
- Comentarios inadecuados o ausentes.

## Deuda técnica y las consecuencias del fallo de las características

## Evaluar el Costo de los Cambios
- N = *Costo de hacer el cambio sin el mecanismo:*
	- Costo de crear el mecanismo + (N* Costo de hacer el cambio usando el mecanismo)
- N: Número anticipado de modificaciones utilizando el mecanismo.
- *Costo de hacer el cambio sin el mecanismo:* Costo de implementar cambios directamente en el código fuente cuando se necesite, sin ningún soporte o herramienta que facilite el proceso.
- *costo de crear el mecanismo:* Costo de desarrollar o adquirir un mecanismo que facilita futuros cambios en el software.
- *Costo de hacer el cambio usando el mecanismo:* Costo de realizar modificaciones con el mecanismo. En gral, es más bajo que hacer cambios directamente en el código.

## ¿Cómo interpreto la fórmula?
N = Costo de hacer el cambio sin el mecanismo >= Costo de crear el mecanismo + (N * Costo de hacer el cambio usando el mecanismo)
- Si el costo total de hacer N cambios sin un mecanismo es mayor o igual que el costo de crear el mecanismo más el costo de usarlo, entonces es justificable invertir crear el mecanismo.

Escenarios de atributos de calidad
## Costo de hacer el cambio sin el mecanismo
Esfuerzo necesario para modificar o adquirir un mecanismo que facilite futuros cambios. Puede incluir herramientas, scripts de automatización o arquitectura de software diseñada para ser fácilmente modificable considerar:
- *Desarrollo *


## Elementos del escenario general
- *Estímulo:* Es una condición que requiere una respuesta cuando llega al sistema.
- *Fuente del estímulo:* Es una entidad que generó el estímulo.
- *Ambiente:* El evento ocurren en ciertas condiciones. Es el estado o en que se encuentra el sistema.
- *Artefacto:* El sistema o parte de él que es estimulada.
- *Respuesta:* Es la activación emprendida como resultado de la llegada del estímulo.
- *Medida de la respuesta:* Cuando ocurre la respuesta, se debe medir de alguna forma para que el requisito se pueda verificar.
Existen un escenario general por atributo de calidad y varios escenarios concretos para el sistema que se está diseñando.

## Escenario para general para disponibilidad
- Source
- Stimulus
- Artifact
- Environment
- Response
- Response Messure

## Priorizar escenarios de QA
- Antes de comenzar el diseño, prioriza tus escenarios de atributos de calidad.
- Típicamente, solo los escenarios más importantes pueden ser considerados al inicio del diseño arquitectónico.
- Elije los 5-7 escenarios principales en la primera ronda de diseño.
- Existen dos estrategias principales parar recopilar escenarios de AC: Taller de Atributos de Claidad (QAN y Árbol de Utilidad)