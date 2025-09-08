- El diseño puede (y debe) ser desarrollado de una forma sistemática.
- Las decisiones de diseño deben de justificarse
- Las decisiones de diseño se deben de registrar.
- Se tienen las herramientas para realizar el diseño de arquitectura de una manera *rigurosa y repetible:*
	1. Se obtienen los requisitos de la arquitectura (verificables) como escenarios de calidad.
	2. Se generan hipótesis (soluciones de diseño potenciales) usando las primitivas de diseño documentadas como patrones, tácticas frameworks y arquitecturas de referencia.
	3. Se prueban las hipótesis mediante el análisis de la arquitectura.

## Métodos
Existen varios mérodos de desarrollo de la arquitectura:
- *Viewpoints and Perspectives*
- *Process of Software Architecting*
- *Architecture-Centric Design Method (ACDM)*
- *Attribute-Driven Design*
La mayoría cubren todo el ciclo de vida de la arquitectura pero dan pocos detalles sobre cómo desarrollar la actividad de diseño.

## El diseño es una actividad de transformación

Sistema de administración del servidor de tiempo
- Una compañía de telecomunicaciones quiere expandir su red IP para soportar servicios de VOIP.
- Un aspecto importante que alcanzar este objetivo es la sincronización de los servidores de VOIP y otros equiós. La sincronización pobre resultará en una QoS baja y clientes insatisfechos.
- Para lograr la sincronización, la compañía quiere desplegar un 
- Los servidores de tiempo se conforma en grupos que típicamente corresponden a regiones geográficas.
- Dentro de estas regiones, los servidores de tiempo se organizan jerárquicamente en estratos en donde los servidores de tiempo colocados en el nivel superior de la jerarquía están equipados con el hardware que proveen el tiempo de manera precisa ().
- Los servidores de tiempo en los estratos inferiores usan NTP para solicitar el tiempo de los servidores en los niveles superiores o de sus pares.
- El equipo depende del provisto por los servidores de tiempo así que una prioridad de la compañía es corregir los problemas en los servidores de tiempo tan rápido.
- Además de NTP, los servidores soporta SNMP el cual provee tres operaciones básicas.
	- set() Cambiar un valor de configuración
	- get() Obtener una variable de configuración o datos de desempeño
	- trap() proveer notificaciones de eventos excepciones como la perdida de conexión gps.

## FCAPS
Sistema de administración de acuerdo con el modelo FCAPS
- Fault management: Recnocer, aislar, corregir y llevar una bitácora de fallas que ocurren en la red.
- Configuration management Incluye reunir y almacenar configuraciones de equipos de red, simplificando la configuración de dispositivos. Se lleva un rastreo a los cambios hechos en la configuración de dispositivo.
- Accounting El objetivo es reunir información del dispositivo. En este contexto, esto incluye llevar un rastreo de las versiones de firmware y hardware, el equipo de hardware etc.
- Performance management: Se centra en determinar la eficiencia de la red actual. Al recolectar y analizar los datos de desempeño, la salud de la red puede ser monitoreada.
- Security management: El proceso de controlar el acceso a los activos en la red. 

## Considerando el desempeño
Los clientes se actualizan cuando se recibe trap durante la operación normal.
- trap tiene que se procesado y almacenado
- 5 segundos es lo máximo que es aceptado.
- *Primario se beneficia del CU y logra alcanzar su tarea*
	- *Secundario necesita del sistema para alcanzar ese CU*
## Restricciones
- limitan el intervalo de posibilidades cuando se toma una decisión de diseño.
- Existen decisiones en las que se tienen elección.
- Antes de iniciar el diseño, las restricciones tienen que ser identificadas y justificadas.
	- Restricciones técnicas:
		- Uso de una base de datos legado
		- Uso de un IDE específico.

## Attributte Driven Design 
- Es un método guiado por los concers sobre los atributos de calidad.
- Es un método iterativo de diseño
- Provee un conjunto de pasos detallados para el diseño de la arquitectura.
- Permite que el diseño se realice de una forma sistemática y repetible
- El resultado es predecible.