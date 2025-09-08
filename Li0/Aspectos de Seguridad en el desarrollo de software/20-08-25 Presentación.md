## Ciclo de vida del desarrollo de software
1. Planificación y análisis
2. Diseño
3. Implementación (Desarrollo)
4. Pruebas
5. Despliegue
6. Mantenimiento

## Aspectos básicos de la seguridad
Seguridad
	  *Riesgo:* 
		- Posibilidad de que ocurra un efecto negativo.
		- Surge de la combinación de una amenaza y vulnerabilidad.
	- *Amenaza:*
		- Cualquier situación que pueda explotar una debilidad y causar un daño 
	- *Vulnerabilidad:*
		- Debilidad en el sistema que puede ser aprovechada por un atacante.
	- *Bug:*
		- Error de codificación que llega a afectar el software.
		- No todos los bugs son vulnerabilidades.

*Amenaza* + *Vulnerabilidad* = ***Riesgo***
## Modelos de seguridad para el desarrollo de software
Modelo de seguridad que ayuda a conocer aspectos de seguridad en el desarrollo de software:
1. *CIA*
	- Tres principios:
		- **Confidencialidad:** El que los datos sean accesibles únicamente por los usuarios autorizados.
		- **Integridad:** Garantiza que la información no pueda ser modificada sin autorización.
		- **Disponibilidad:** Que los servicios o métodos siempre estén disponibles para el acceso a los datos.

- Vulnerabilidad del código 
- Inyección de datos.

## Amenazas
1. *Ataques Bot* -> Ataque de fuerza bruta.
2. *Inyecciones de código* -> SQL Injection, Command Injection
3. *Cross-Site Scripting (XSS)* 
4. *Uso de librerías y dependencias vulnerables*
5. *Ingeniería Social*
6. *Exposición de datos Sensibles*

//LTS latest stable

Dado que la *Seguridad cuesta dinero,* el problema fundamental es buscar el *equilibrio* entre el coste de la seguridad y el impacto económico de los riesgos probables.

La seguridad implica costes incluso más allá del coste de los sistemas, software o tiempo de expertos en la configuración.

En el caso del desarrollo de aplicaciones, un software bien protegido es más caro y requiere más *tiempo de desarrollo* que uno que no lo esté. Por otro lado las *intrusiones* con un efecto importante tienen un impacto económico considerable.

Muchas tecnologías de seguridad comienzan a utilizarse cuando son_:
Fáciles de implantar
Los auditores de seguridad comienzan a demandarlas.

![[Pasted image 20250820101614.png]]
## 4 Actores principales
OWASP dice 4 tipos de actores:
1. *Actores de estado( actividad de grupo):* Son un conjunto de grupos que están vinculados al gobierno que realizan operaciones de espionaje, su objetivo es el espionaje, robo de información, golpes de estado, operaciones de desinformación.
2. *Ciberdelincuencia:* Organizaciones o individuos que desean obtener ganancias mediante, ramsonware, robo de credenciales.
3. *Hacktivismo:* Combina el activismo social con técnicas de hacking, no necesariamente quieren dinero buscan llamar la atención o generar causa.
4. *Actores internos:* Personas que tienen acceso legitimo a los sistemas y llegan a abusar sus propios privilegios. Objetivos: Venganza, Espionaje corporativo.

//Métodos de ataque

# Top 10 OWASP 2021

| **Categoría OWASP 2021**                                    | **Método(s) de ataque relacionado(s)**                                                                                               | **Ejemplo práctico**                                                              |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- |
| **A01: Broken Access Control** (Control de acceso roto)     | - Escalada de privilegios- Acceso directo a URLs sin autorización- Manipulación de parámetros                                        | Usuario normal que accede a `/admin/panel` sin estar autorizado.                  |
| **A02: Cryptographic Failures** (Fallos criptográficos)     | - Ataques de fuerza bruta sobre cifrados débiles- Ataques de padding oracle- Interceptación de datos en tránsito (MITM)              | Uso de **HTTP en vez de HTTPS**, robo de contraseñas en texto plano.              |
| **A03: Injection** (Inyección)                              | - **SQL Injection**- **NoSQL Injection**- **Command Injection**- **LDAP Injection**- XSS (ahora integrado aquí)                      | Ingresar `"' OR '1'='1"` en un formulario de login para acceder sin credenciales. |
| **A04: Insecure Design** (Diseño inseguro)                  | - Lógica de negocio manipulable- Saltarse validaciones por mal diseño- Abuso de flujos de la aplicación                              | Un e-commerce que permite aplicar un **cupón ilimitadas veces**.                  |
| **A05: Security Misconfiguration** (Configuración insegura) | - Ataques a servicios con **credenciales por defecto**- Directorios listados públicamente- Servidores con debugging habilitado       | Acceso a `/phpmyadmin/` con usuario `root` y contraseña vacía.                    |
| **A06: Vulnerable and Outdated Components**                 | - Explotación de vulnerabilidades conocidas (CVEs)- Uso de librerías/frameworks sin parches                                          | Exploits de **Log4Shell (Log4j)** en sistemas desactualizados.                    |
| **A07: Identification and Authentication Failures**         | - **Fuerza bruta de contraseñas**- Robo de sesiones (Session Hijacking)- Credential stuffing                                         | Intentar miles de contraseñas hasta lograr acceso.                                |
| **A08: Software and Data Integrity Failures**               | - Manipulación de actualizaciones de software- **Insecure Deserialization** (inyectar objetos maliciosos)- Ataques a pipelines CI/CD | Infectar una librería usada en el proyecto (**supply chain attack**).             |
| **A09: Security Logging and Monitoring Failures**           | - Encubrimiento de ataques- Bypass de auditoría- No detección de intrusiones                                                         | Un atacante entra varias veces sin ser detectado porque **no hay logs**.          |
| **A10: Server-Side Request Forgery (SSRF)**                 | - Forzar al servidor a hacer peticiones HTTP hacia otros sistemas internos o externos                                                | Usar un campo de URL para que el servidor acceda a `http://localhost:8080/admin`. |

# Ataques 
| **Tipo de ataque**                             | **Descripción**                                                           | **Ejemplo real**                                                | **Relación con OWASP**                                                                                                                                                                                 |
| ---------------------------------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **DDoS (Denial of Service / Distributed DoS)** | Saturar un servidor con tráfico masivo para que deje de responder.        | Un sitio web cae porque miles de bots lo inundan de peticiones. | No está directamente en el OWASP Top 10 (porque es un ataque de infraestructura), pero puede aprovechar **A10:2021-SSRF** o **A05:2021-Misconfiguración** si no hay defensas como WAF o rate limiting. |
| **Ransomware**                                 | Malware que cifra los archivos y pide rescate para liberarlos.            | WannaCry (2017).                                                | Relacionado indirectamente con **A06: Componentes vulnerables** (si se aprovecha software desactualizado) y **A08: Integridad de datos y software** (si se manipula el pipeline de actualizaciones).   |
| **Phishing / Spear Phishing**                  | Engañar al usuario para que entregue credenciales o instale malware.      | Correos falsos de “soporte bancario”.                           | No aparece como categoría OWASP, pero suele explotar fallos de **A07: Identificación/Autenticación** (si roban contraseñas) o **A02: Fallos criptográficos** (si no hay MFA/HTTPS).                    |
| **Malware / Troyanos**                         | Software malicioso que se instala en el sistema para robar datos o dañar. | Keyloggers que capturan lo que escribes.                        | Puede relacionarse con **A06: Componentes vulnerables** o **A08: Integridad de software** si se distribuye por librerías infectadas.                                                                   |
| **Ataques de fuerza bruta**                    | Probar miles de contraseñas hasta encontrar la correcta.                  | Crackeo de cuentas con diccionarios de contraseñas.             | Directamente relacionado con **A07: Fallos de identificación/autenticación**.                                                                                                                          |
| **Ingeniería social**                          | Manipulación psicológica para obtener acceso o información.               | Un atacante llama fingiendo ser de TI y pide credenciales.      | No está en OWASP (es humano, no técnico), pero es un vector inicial para explotar categorías como **A01: Control de acceso roto**.                                                                     |
| **Ataques MITM (Man in the Middle)**           | Interceptar la comunicación entre cliente y servidor.                     | Falsos puntos Wi-Fi que roban credenciales.                     | Se relaciona con **A02: Fallos criptográficos**, si no se usa HTTPS/TLS.                                                                                                                               |
| **Supply Chain Attacks**                       | Infectar librerías, dependencias o actualizaciones de software.           | Caso SolarWinds (2020).                                         | Directamente en **A08: Integridad de software y datos**.                                                                                                                                               |