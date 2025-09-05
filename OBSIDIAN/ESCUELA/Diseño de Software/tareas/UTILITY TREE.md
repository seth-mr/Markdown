


## Sistema elegido

**Sistema:** Eminus (plataforma institucional de gestión del aprendizaje de la UV).

### Justificación 
**¿Que hace el sistema?**

Eminus es el *sistema oficial* de gestión del aprendizaje de la *Universidad Veracruzana.*  
Permite a estudiantes y profesores *realizar actividades de enseñanza-aprendizaje* en línea:  

subir tareas, entregar proyectos, responder cuestionarios, participar en foros, revisar calificaciones, entre otros.

**¿Quiénes son los stakeholders principales?**

- **Estudiantes:** requieren acceso a *materiales y actividades en línea* en todo momento.  
- **Profesores:** necesitan una *interfaz confiable* para publicar contenidos, revisar entregas y asignar calificaciones.  
- **Administradores TI:** deben *garantizar disponibilidad, seguridad y soporte técnico.*  
- **La institución:** busca garantizar la continuidad académica, asegurar la privacidad de los datos y dar una experiencia adecuada a toda la comunidad universitaria.

**¿Qué decisiones de negocio condicionan su diseño?**

- La necesidad de *disponibilidad continua* ya que es una plataforma oficial 
- La *seguridad* pues maneja datos personales y académicos sensibles.  
- La *escalabilidad* para soportar alta carga durante inscripciones y evaluaciones. 
- La *usabilidad* porque debe ser intuitiva para miles de estudiantes y profesores con distintos niveles de expertis.  

---

## Selección de atributos de calidad

- **Performance (Desempeño):**  
  Eminus debe *responder con rapidez* en durante la alta demanda, como la temporada de inscripción, entrega de exámenes en línea, o revisión masiva de calificaciones.  
  **Justificación:**  
  El desempeño es fundamental porque la plataforma es *utilizada  por miles de estudiantes y profesores*. Durante exámenes o inscripciones,  miles de usuarios pueden realizar solicitudes al mismo tiempo *cualquier retraso o bloqueo puede generar  errores* en la entrega de tareas o exámenes
  Un buen desempeño no solo implica velocidad en la respuesta del sistema, sino también la capacidad de manejar múltiples procesos y garantizar que la experiencia del usuario no sea de mala.  Elijo este atributo porque sin un rendimiento adecuado, perdería valor académico..

- **Availability (Disponibilidad):**  
  Debe estar disponible 24/7, con tiempo mínimo de inactividad, porque que es el *software oficial* académico para estudiantes y profesores.  
  **Justificación:**  
  La disponibilidad es crítica porque la plataforma es el *canal oficial de enseñanza-aprendizaje.* Una caída del sistema durante la entrega de proyectos, revisiones de exámenes o consultas de calificaciones puede interrumpir la vida académica y generar retrasos administrativos .  
  Este atributo asegura que la plataforma funcione incluso durante mantenimientos programados o fallos inesperados. Su inclusión como atributo de calidad es a causa de la *necesidad de garantizar un servicio confiable*

- **Security (Seguridad):**  
  El sistema gestiona *datos  sensibles*: información personal de los usuarios, contraseñas, calificaciones y registros .  
  **Justificación:**  
  La seguridad es prioritaria porque cualquier vulneración puede tener consecuencias graves para los estudiantes, profesores y la institución. Accesos no autorizados, ataques de fuerza bruta, o robo de datos podrían *comprometer la confidencialidad, integridad y disponibilidad de la información*.  
  Este atributo lo eleiji  para garantizar que la plataforma implemente controles de acceso , cifrado de datos, autenticación  y monitoreo constante de seguridad.

- **Usability (Usabilidad):**  
  La interfaz debe ser intuitiva y dejar  a los usuarios *completar actividades sin necesidad de capacitación* , facilitando la adopción del sistema por estudiantes y profesores.  
  **Justificación:**  
  La usabilidad asegura que la *plataforma sea accesible y fácil* de navegar para usuarios con distintos niveles de experiencia digital. Esto un entorno educativo donde la diversidad de usuarios es alta, incluyendo estudiantes jóvenes y profesores con distintas  edades.  
  Una *buena usabilidad reduce errores* en la entrega de tareas, la configuración de cursos o la gestión de evaluaciones, y disminuye la carga sobre el soporte técnico. Además, fomenta el compromiso y la satisfacción del usuario.

---

##  Escenarios de atributos de calidad 

### **Performance**

**Escenario 1**  
- *Source:* 2000 estudiantes  
- *Stimulus:* Ingresan al mismo tiempo para pagar la inscripcion
- *Artifact:* Servidor de base de datos y aplicación  
- *Environment:* Hora pico de inscripciones  
- *Response:* El sistema procesa todas las solicitudes sin rechazar conexiones  
- *Response Measure:* Tiempo de respuesta ≤ 15 segundos por acción  
- *Valor:* H 
- *Riesgo:* H

**Escenario 2**  
- *Source:* Profesor  
- *Stimulus:* Sube un archivo de 100 MB a la plataforma   
- *Artifact:* Servidor de almacenamiento  
- *Environment:* Clase regular  
- *Response:* El archivo se carga sin interrupciones  
- *Response Measure:* Tiempo de carga ≤ 15 segundos  
- *Valor:* M 
- *Riesgo:* L  

---

### **Availability**

**Escenario 1**  
- *Source:* Estudiantes  
- *Stimulus:* Acceden durante una actualización de sistema  
- *Artifact:* Plataforma completa  
- *Environment:* Ventana de mantenimiento programado  
- *Response:* Acceso bloqueado temporalmente con mensaje informativo  
- *Response Measure:* Máximo downtime permitido: 30 min/mes  
- *Valor:* H 
- *Riesgo:* H  

**Escenario 2**  
- *Source:* Fallo en el servidor principal  
- *Stimulus:* Apagón en el data center  
- *Artifact:* Infraestructura de hosting  
- *Environment:* Periodo de clases  
- *Response:* Conmutación automática al servidor de respaldo  
- *Response Measure:* Recuperación ≤ 10 minutos  
- *Valor:* H 
- *Riesgo:* H  

---

### **Security**

**Escenario 1**  
- *Source:* Atacante externo  
- *Stimulus:* Intenta vulnerar el login con fuerza bruta  
- *Artifact:* Sistema de autenticación  
- *Environment:* Operación normal  
- *Response:* Sistema bloquea el acceso tras 3 intentos fallidos y notifica al administrador  
- *Response Measure* Bloqueo inmediato tras 3 fallos consecutivos  
- *Valor:* H 
- *Riesgo:* H  

**Escenario 2**  
- *Source:* Usuario autenticado  
- *Stimulus:* Intenta acceder a calificaciones de otro alumno  
- *Artifact:* Base de datos de usuarios y cursos  
- *Environment:* Sesión activa  
- *Response:* Acceso denegado y evento registrado en logs  
- *Response Measure:* 100% de intentos indebidos bloqueados  
- *Valor:* H 
- *Riesgo:* M  

---

### **Usability**

**Escenario 1**  
- *Source:* Estudiante nuevo  
- *Stimulus:* Ingresa por primera vez a Eminus  
- *Artifact:* Interfaz gráfica del portal  
- *Environment:* Navegador web estándar  
- *Response:* Encuentra su curso y verifica el plan de este. 
- *Response Measure:* ≤ 15 minutos en completar la acción básica  
- *Valor:* M 
- *Riesgo:* L  

**Escenario 2**  
- *Source:* Administrador  
- *Stimulus:* Actualiza las calificaciones de los estudiantes de un curso.
- *Artifact:* Módulo de Calificaciones  
- *Environment:* Navegador web estándar  
- *Response:* La actualizacion se lleva a cabo sin errores
- *Response Measure:* ≤ 25 minutos en configurar y publicar  
- *Valor:* H 
- *Riesgo:* M  



## Representacion grafica 

![[d2(1).png|719x724]]



___ 

## Reflexion final

- **¿Qué retos encontraste al formular escenarios?**
- 
	1. Principalmente el encontrar un *escenario realista y comun* que pudiera asociarse con los subatributos de calidad que elegi.
	
	2. No me sentia comodo con ningun *software para crear diagramas* por lo que investigue y encontre el idioma d2



- **¿Cuál de los escenarios H/H consideras más crítico y por qué?**

	El escenario mas critico que elegi fue el que corresponde al atributo de *Security* y al subatributo de *Authentication*, un ataque de fuerza bruta por los siguientes motivos.

	- *Impacto directo en la seguridad:* si logran vulnerar el login, pueden robar nuestra informacion.
	- *Perdida de confianza en la institución:* es posible que la universidad pierda parte de su prestigio y postulantes si se sabe que la informacion que guardan puede ser robada 
	- *Difícil migración:* por la magnitud del sistema seria muy complejo el reparar las brechas de seguridad o en su defecto el migrar a otro sistema.


- **¿Qué decisiones arquitectónicas anticipas como respuesta a estos ASRs**

	- **Performance (Desempeño):**  
     implementaría *escalabilidad horizontal* 
         
- **Availability (Disponibilidad):**  
    Configuraría *servidores redundantes* para garantizar operación continua 
    
- **Security (Seguridad):**  
    Implementaria una **autenticación robusta**
    
- **Usability (Usabilidad):**  
     *interfaces intuitivas*,  para facilitar el uso.


