# Características arquitectónicas

- Estos son *atributos de calidad o -ilities*.
- *Criterios de éxito* del sistema más allá de la funcionalidad.
- *Ejemplo:* La seguridad y la disponibilidad son más importantes que la interfaz gráfica

## Decisiones arquitectónicas
- Son elecciones de diseño con impacto a largo plazo.
	- Microservicios vs. monolito; SQL vs. NoSQL; política de redundancia.
- "All architecture is about trade-offs." Richards & Ford
- *Ejemplo:* Un banco que prioriza disponibilidad puede elegir redundancia de servidores a costa de mayor costo.

## Componentes lógicos
- Bloques funcionales que representan el dominio.
- *Ejemplo:* Cuentas, pagos, préstamos, notificaciones.
- No son el código final, sino abstracciones que guían el diseño y el mantenimiento

## Estilos arquitectónicos
- Plantillas que definen cómo se organizan los componentes.
- *Ejemplos:* capas, cliente-servidor, microservicios, event-driven.

## Caso de estudio: Banco Digital
- Usuarios acceden por *App móvil, Web y Cajeros automáticos.*
- Un *backend (Servidor) distribuido con micro-servicios* maneja cuentas, pagos, créditos.
- Los datos se guardan en *bases de datos* seguras (transacciones críticas y auditoría).
- La *infraestructura* es *híbrida* (nube + centro de datos propio) por temas de seguridad y regulación.

¿Qué es una CDN?

//Poner ¿Por qué se realizo esto?
## Decisiones arquitectónicas
- Microservicios vs. monolito -> se eligen microservicios para permitir releases independientes.
- Separar cuentas y pagos.
- Usar un DB transaccional para operaciones críticas.

## Características arquitectónicas
- *Seguridad:* Cifrado y autenticación multifactor
- *Disponibilidad:* alta redundancia (99.99%)
- *Escalabilidad:* auto-scaling horizontal
- *Facilidad de evolución:* versionado de APIs

Como escalan los sistemas horizontalmente y como escalan verticalmente

## Escenarios de calidad (light)
- *Disponibilidad*
	- Si un servidor falla en plena operación, otro entra de inmediato en funcionamiento para que el servicio no se interrumpa
		- El sistema sigue activo aun en caso de fallos.
- *Escalabilidad:*
	- En día de quincena, cuando el número de transacciones se multiplica el sistema agrega capacidad.
- *Seguridad:*
	- Si alguien intenta acceder de forma no autorizada, el sistema detecta el intento y bloque la entrada antes de que comprometa los datos.
		- Se protege la información de accesos indebidos.
- *Facilidad de evolución:*
	- Si entra en vigor una nueva regulación puede actualizarse rápidamente sin detener operaciones ni afectar a los clientes.
		- Se adapta con agilidad a cambios externos.

## Componentes lógicos
- *Cuentas:* apertura, saldos, movimientos.
- *Pagos:* transferencias, SPEI, tarjetas.
- *Créditos:* solicitud y pagos(amortizaciones).
- *Notificaciones:* correo, SMS, push.
- *Cumplimiento Normativo:* auditoría, antifraude, reportes, regulatorios.

## Estilo arquitectónico
- Microservicios distribuidos con mensajería asíncrona.
- Integración con sistemas legacy vía adaptadores.
- Observabilidad integrada

*La arquitectura de un sistema bancario no es solo un diagrama bonito.*

*Son decisiones técnicas que permiten garantizar seguridad, continuidad en la operación y cumplimiento regulatorio.*

# Arquitectura de software
"Arquitecture is about the important stuff... whatever that is."
-Ralph

"All architecture is design, but not all design is architecture"
-Grady Booch

La arquitectura de software de un sistema es el *conjunto de software, las relaciones entre ellos y las propiedades de ambos de *estructuras* necesarias para *razonar* acerca de un *sistema*, que comprenden los *elementos* las relaciones entre ellos y las propiedades de ambos.

## Elemento arquitectónico
- *Definición:*
	- Un elemento arquitectónico es una unidad fundamental en la arquitectura de un sistema.
	- Puede ser un componente, un conector o un módulo, entre otros.
- *Tipos de elementos Arquitectónicos.*
	- Componentes:
		- Partes principales de un sistema que realizan funciones específicas: Ejemplo Un servicio en una arquitectura de microservicios.
	- Conectores:
		- Mecanismos de comunicación entre componentes. Ejemplo: Un bus de datos o una API REST.
	- Módulos:
		- Agrupaciones lógicas de componentes y conectores que forman una unidad más gran del sistema: Ejemplo un subsistema o un paquete de software.

## La arquitectura es...
*Un conjunto de estructuras de software*
- La arquitectura involucra múltiples estructuras de software.
- Una estructura = conjunto de elementos + una relación
- Ninguna estructura única define toda la arquitectura.
- *Categorización de estructuras*
	- Componentes y conectores
	- Módulos 
	- Asignación
- No todas las estructuras son arquitectónicas.
	- Ej: Líneas de código fuente con la letra "z" (no arq.)
- Criterios para estructuras arquitectónicas.

## La arquitectura es una abstracción
- Composición de la arquitectura
	- Estructuras = elementos + Relaciones
	- Arquitecturas = Elementos de software y cómo se relacionan.
- Omisión Intencional:
	- Se omiten detalles no útiles para el razonamiento sobre el sistema.
- Arquitectura como abstracción:
	- Selecciona ciertos detalles y suprime otros

## Interfaces y división
- Interacción de elementos:
	- A través de interfaces que dividen detalles en públicos y privados.
- Enfoque Arquitectónico:
	- Se centran en los detalles públicos.
	- Los detalles privados no son parte de la arquitectura.

## Abstracción en Arquitectura
- *Esencial para:*
	- Manejar la complejidad del software.
	- Maximizar nuestra capacidad cognitiva limitada.
- *Con esto la arquitectura:*
	- Facilita la comprensión del sistema sin necesidad de conocer cada detalle.

## Vistas
- *Analogía con la Naturaleza:*
	- Diferencia especialistas tienen distintas perspectivas sobre las estructuras del cuerpo humano (neurología, ortopedia, dermatología, etc.).
	- Estas perspectivas juntas describen la "arquitectura" del cuerpo humano.
- *Analogía con la Construcción:*
	- Profesiones como electricistas y plomeros se enfocan en diferentes estructuras de un edificio.

## Tres Tipos de Estructuras Arquitectónicas
- **Estructuras de componentes y Conectores (C&C):**
	- Se enfocan en la interacción de los elementos en tiempo de ejecución para realizar las funciones del sistema.
	- Componentes: Unidades principales de computación con comportamiento en tiempo de ejecución (servicios, clientes, servidores, etc.).
	- Conectores: Vehículos de comunicación entre componentes (llamadas, sincronización, pipes, etc.).
- Preguntas Clave:
	- ¿Cuáles son los principales componentes en ejecución y cómo interactúan?
	- ¿Cómo progresa la información a través del sistema?
	- ¿Qué partes pueden ejecutarse en paralelo?
	- Puede cambiar la estructura del sistema durante la ejecución?
- **Estructuras de Módulos:**
	- Dividen el sistema en unidades de implementación llamadas módulos. Ejemplos: Clases, paquetes, capas.
	- **Características de los Módulos:**
		- Muestran cómo el sistema se estructura en unidades de código o datos.
		- Asignación de responsabilidades computacionales específicas.
		- Base para asignaciones de trabajo en equipos de programación.
	- **Relaciones entre Módulos:**
		- Tipos: "Usa", generalización (herencia), "es parte de."
	- **Preguntas Clave:**
		- ¿Cuál es la responsabilidad funcional principal de cada módulo?
		- ¿Qué otros elementos de software puede usar un módulo?
		- ¿De qué otros módulos depende?
- **Estructuras de Asignación:**
	- Mapean estructuras de software a estructuras no relacionadas con software (organización, entornos de desarrollo, etc.).
	- **Características de las Estructuras de Asignación:**
		- Mapeo a Infraestructura Física:
			- Relacionan componentes de software con hardware específico (por ejemplo, procesadores o servidores).
		- Mapeo a Estructuras Organizacionales:
			- Asignan módulos a equipos de desarrollo o localidades físicas.
		- Mapeo a Entornos de Desarrollo:
			- A que ambientes de su desarrollo, prueba y construcción están destinados en particular.
		- Preguntas Clave:
			- ¿En qué procesador(es) se ejecuta cada elemento de software?
			- ¿Cómo se asignan los elementos de software a los equipos de desarrollo?
			- ¿Qué impacto tiene el entorno de ejecución en el rendimiento del sistema?

## Big Ball of Mud
Es una jungla de código de espagueti estructurada al azar, en expansión, descuidada, con cinta adhesiva y alambre para embalar. 

Es posible que la estructura general del sistema nunca haya sido bien definida.

Arquitectura erosionada.

//Ley de Conway

"Any organization that designs a system will produce a design whose structure is a copy of the organization's communications structure"
-Melvin E. Conway (1967)

"The structure of any system designed by an organization is isomorphic "


"If you have four groups working on a compiler, you'll get a 4-pass compiler."
-Eric S. Raymond(1996)

## Reflexión sobre la ley de Conway
- Al estructurar o reestructurar equipos, considera cómo esta estructura puede influir en la arquitectura del software que producen.
- Aprovecha la Ley de Conway en lugar luchar contra ella.