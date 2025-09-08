
- El diseño puede y debe ser desarrollado de una forma sistemática
- Las decisiones de diseño deben justificarse
- Las decisiones de diseño se deben de registrar


1. Se obtienen los r*requisitos de la arquitectura*(verificables) como escenarios de calidad
2. Se *generan hipótesis* usando las primitivas de diseño documentadas como patrones,tácticas, frameworks y arquitecturas 
3. Se *prueban las hipótesis* mediante el análisis de la arquitectura


definir conductores de la arquitectura -> definir la arquitectura -> diseñar la arquitectura -> documentar la arquitectura -> evaluar

### Requerimientos de la arquitectura

- Casos de uso primarios
- Quality atributes/ requeriments
- Constraints


## MÉTODOS
### Ejemplo

Una empresa de telecomunicaciones *busca expandir su red IP para soportar VoIP*. Un aspecto importante para lograr esto es:

- *Sincronización de servidores de VoIP y otros equipos*  
- La compañía quiere desplegar una *red de servidores que soporten NTP*

Los servidores de tiempo se conforman en grupos que típicamente corresponden a regiones geográficas.

Dentro de estas regiones, los servidores están organizados jerárquicamente en estratos, en donde:

- Los servidores de tiempo colocados *en el nivel superior de la jerarquía están equipados con el hardware que provee el tiempo de manera precisa*  
- Los servidores de tiempo en los estratos inferiores usan *NTP* para solicitar el tiempo de los servidores en niveles superiores o de sus pares

El equipo depende del tiempo provisto por los servidores de tiempo tan pronto sea posible.  
Otra prioridad es monitorear datos de los servidores para supervisar el desempeño de la red.

Además de NTP, los servidores soportan **SNMP**, el cual provee *3 operaciones básicas*:

- *set()*: Cambiar un valor  
- *get()*: Para obtener un dato  
- *trap()*: Proveer notificaciones de eventos excepcionales como la pérdida o falla

Se ha decidido el desarrollo de un *sistema de administración de los servidores de tiempo*.

Una vez desplegada la red, la compañía planea *extenderla para agregar muchos más servidores*, entre ellos otros que también soporten otros protocolos diferentes de SNMP.

El sistema debe estar de acuerdo con el modelo **FCAS**, el cual es un *estándar para la administración de redes*.

---

### Modelo FCAPS

FCAPS es un *modelo de gestión de redes ISO* (Organización Internacional de Normalización) que define cinco categorías funcionales para la administración de una red:

- **Falla (Fault)**: Reconocer y aislar errores  
- **Configuración (Configuration)**: Reunir y almacenar configuraciones de equipos en red  
- **Contabilidad (Accounting)**: Llevar un registro del dispositivo, rastreo de versiones de firmware y hardware  
- **Desempeño (Performance)**: Determinar la eficiencia de la red actual y almacenar datos para analizarlos y mejorarlos  
- **Seguridad (Security)**: Controlar el acceso


## AUTO-DRIVEN-DESING

![[image-2.png]]


- es un metodo generado por los concerns sobre los atributos de calidad


### Objetivos de diseño


**TIpo de sistema** De campo verde en un dominio maduro (el campo es verde y se puede llegar a machetear)

**Objetivo** Diseñar para la construcción de un incremento de sistema 

**Preocupaciones** Estructura del sistema, organización, de la base de codigo, validación de las entradas de manejo de las excepciones

### Casos de usos principales

Son criticos para alcanzar los objetivos del negocio

- Estan asociados con un escenario de un atributo de calidad importante+
- Podria implicar un alto grado de dificultat tecnica
- Ejercita varios elementos arquitectonicos
- Representa una *familifa* de casos de usos
- solo el 10-20 % de los casos de uso son principales 


### Desiciones de diseño

se seleccionan dos arquitecturas de diferencia

se selecciona 3-tier como patron de despliegue


