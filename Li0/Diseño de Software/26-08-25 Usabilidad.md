## Retroalimentación de la actividad
Esto les permitió observar, desde la perspectiva del usuario, diversos problemas en la interacción:
- Falta de *visibilidad del estado del sistema:* la aplicación no siempre comunica claramente qué está ocurriendo después de una acción.
- *Inconsistencias* entre pantallas o funciones, lo que obliga al usuario a reaprender cada vez.
- Uso de *terminología técnica o interna* que no corresponde con el lenguaje del dominio del usuario.
- Dificultades para *recuperarse de errores,* ya que no siempre hay mensajes claros ni opciones de deshacer.
*Reflexión clave:* Aunque en la práctica se evaluaron síntomas "visibles" en la interfaz, muchos de estos problemas *tienen raíces más profundas, en la arquitectura de software.*

1. *Si no hay feedback inmediato* La causa no siempre está en el diseño de la pantalla, Puede deberse a que la arquitectura carece de un mecanismo de *notificación en tiempo real*
2. *Las inconsistencias entre pantallas*

La heurística es útil para evidenciar problemas de usabilidad desde la perspectiva del usuario, pero la *solución estructural* exige pensar en la  *arquitectura de software.*

## Definición de usabilidad
Según la ISO/IEC 25010:2011 Es el grado en el que un producto o sistema puede ser utilizado por usuarios específicos para lograr objetivos específicos con efectividad, eficiencia y satisfacción en un contexto de uso especificado.

La usabilidad *no solo estética ni diseño gráfico*, es un atributo de calidad que debe verificarse y evaluarse en escenarios arquitectónicos.

Diferenciar:
- *Usabilidad:* Atributo de calidad con métricas observables.
- *Experiencias de usuario (UX)* Disciplina más amplia que incluye percepciones y emociones, no todas controlables desde la arquitectura.

## Tácticas arquitectónicas para la usabilidad.
1. Mejorar la capacidad del usuario para comprender el sistema.
	- *Consistencia:* Decisiones arquitectónicas que fuerzan la uniformidad de flujos y operaciones.
	- *Modelo conceptual explícito:* Reflejar en la estructura de módulos el modelo de tareas del dominio.
	- *Reducir complejidad visible:* Uso de capas y encapsulación que oculten detalles técnicos irrelevantes para el usuario.
2. Reducir la carga de trabajo del usuario
	- *Automatización de tareas repetitivas* Incluir componentes que validen, completen valores por defecto o sugieren acciones.
	- *Personalización y adaptación:* Mecanismo de almacenamiento de preferencias y perfiles de usuario.
	- *Soporte a accesibilidad e internacionalización:* Integrados como servicios transversales  en la arquitectura.
3. Aumentar la confianza del usuario en el sistema
	- *Feedback inmediato:* Soportado por conectores que garanticen comunicación en tiempo real (eventos, colas mensajería).
	- *Prevención de errores:* Validaciones centralizadas, restricciones arquitectónicas que eviten estados inconsistentes.
	- *Recuperación de errores:* Módulos que aseguren mensajes de error consistentes y mecanismos de rollback.

## ¿Qué es desplegar software?
*Definición:* Proceso de hacer que un software esté disponible para su uso.
- Asegura que el software funcione correctamente en el entorno de producción.
- Permite la entrega de nuevas características y correcciones.
- Minimiza el tiempo de inactividad y los errores.

*Rollback:* Proceso de revertir un despliegue si se detectan problemas.

## Métodos de Despliegue
- *Despliegue Manual:* Control completo, pero más propenso a errores y más lento.
- *Despliegue Automático Básico:* Utiliza scripts para automatizar algunos pasos, mayor rapidez.
- *Despliegue Automatizado Completo (CI (Integración Continua) /CD (Entrega Continua))* Todo el proceso es automático, ideal para grandes proyectos y despliegues frecuentes.
![[Pasted image 20250826115715.png]]![[Pasted image 20250826115815.png]]

## Evolución en los Ciclos de Despliegue
- En el pasado, los despliegues de software eran poco frecuentes y acumulaban muchas actualizaciones.
- Se realizaban despliegues mensuales, trimestrales o incluso anuales.
- *Presión Competitiva*
	- Especialmente en e-commerce, la competencia ha llevado a ciclos de despliegue mucho más cortos.
	- Los despliegues pueden ocurrir varias veces al día.

## Despliegue Continuo
- *Proceso automatizado* desde la codificación hasta la interacción de los usuarios reales con el sistema en producción.
- *No* requiere *intervención humana* para poner el sistema en producción.

*Entrega continua:*
Similar al despliegue continu


## Pipeline de Despliegue
- Secuencia de herramientas y actividades que comienza con el registro (push) del código en un sistema de control de versiones y finaliza con el despliegue de la aplicación.
- Incluye la configuración de la infraestructura en donde se desplegará el software.
- Incluye también integración, pruebas automáticas de funcionalidad, rendimiento, seguridad y cumplimiento de licencias.

## Entornos en el Pipeline de Despliegue
*Entorno de Desarrollo:*
- Desarrollo de código y ejecución de pruebas unitarias para módulos individuañes.
- Código revisado  y enviado al control de versiones.
*Entorno de Integración*
- Construye una versión ejecutable del servicio.
- Un servidor de integración continua compila el código nuevo o modificado junto con las versiones compatibles más recientes del código de otros módulos.
- Realiza pruebas unitarias y de integración para el sistema completo.
- Si pasan las pruebas, el servicio se promociona al entorno de staging.
*Entorno de Staging:*
- Pruebas de rendimiento, seguridad, conformidad de licencias y pruebas de usuario.
- Uso de simuladores para sistemas embebidos.
- Despliegue en producción después de pasar todas las pruebas, usando modelos como blue/green o actualizaciones continuas.
*Entorno de Producción:*
- Monitoreo cercano hasta garantizar la calidad del servicio.
- Si se detectan problemas, es posible revertir a una versión anterior mientras se resuelven los defectos.

## Ejemplo básico de Pipeline de Despliegue
1. *Desarrollo:* Push de Código al repositorio remoto.
2. *CI Pipeline:* Compilación -> Pruebas unitarias -> Análisis de código.
3. *Integración_:* Integración de Código -> Pruebas de integración.
4. *Staging:* Despliegue en Staging -> Pruebas de Usuario y QA -> Pruebas de seguridad y rendimiento.
5. *Producción:* Despliegue en Producción -> Monitoreo Post-Despliegue

## Efecto de la Virtualización en los Entornos
*Entornos Físicos Tradicionales*
- Cada entorno (desarrollo, integración, staging) consistía en hardware específico operado por diferentes equipos.
- Las diferencias de hardware causaban problemas de inconsistencias en las pruebas entre entornos.

## Beneficios de la Virtualización
- *Paridad de Entornos* Virtualización permite que los entornos difieren en escala pero no en tipo de hardware o estructura.
- *Herramientas de Aprovisionamiento:* Facilitan la creación de entornos comunes que imitan el entorno de producción lo más cerca posible.
- *Reducción de Inconsistencias:* Menos tiempo resolviendo problemas causados por diferencias de entorno.

Para saber más Capítulo 16

## Ventajas del Despliegue Continuo
- *Corrección Rápida de Errores:* Los errores se pueden solucionar  y liberar inmediatamente.
- *Liberación de Nuevas Funcionalidades:* Las nuevas características no necesitan esperar a la próxima liberación programada.
*Limitaciones*
- No es viable en todos los dominios, especialmente en sistemas con muchas dependencias, sistemas embebidos, o aquellos en ubicaciones de difícil acceso.

## Facilidad de despliegue
- *Definición:* Propiedad del *software* que indica que puede ser *Desplegado* en un entorno de ejecución dentro de un *tiempo, esfuerzo y riesgo predecibles y aceptables.*
- Incluye la posibilidad de *revertir* el despliegue si no cumple con las especificaciones.
- Es crucial para la entrega continua y despliegue continuo, permitiendo un despliegue rápido y confiable de los *cambios en* la *producción*.

## Implicaciones del despliegue
- Diseñar para la facilidad de despliegue implica razonar sobre la pipeline de despliegue,  *asegurando tiempos y esfuerzos predecibles* para el despliegue.
- Incluye *automatizar el proceso* de despliegue.
- *Minimizar* las *diferencias* entre entornos.
- *Separar* la *aplicación y* la *configuración*
## Medición de la Calidad del Pipeline de Despliegue
*Tiempo de Ciclo*
- Mide la rapidez con la que se avanza a través del pipeline.
- Organizaciones con despliegues frecuentes (varias o cientos de veces al día) requieren mínima intervención humana y coordinación entre equipos.
*Trazabilidad*
- Capacidad de recuperar todos los artefactos que llevaron a un problema en un elemento.
- Incluye código, dependencias, casos de prueba y herramientas utilizadas.
- La información de trazabilidad es almacenada en un base de datos de artefactos.
*Repetivilidad*
- Obtener el mismo resultado al realizar la misma acción con los mismos artefactos.
- Ejemplos de desafíos: versiones de bibliotecas cambiantes y modificaciones de bases de datos por pruebas anteriores.

## Aspectos a considerar en el Despliegue
**Llegada al Host:¿Cómo llega el software a la máquina donde se ejecutará?**
- *Método de Entrega*
	- *Push:* Las actualizaciones se despliegan automáticamente sin solicitud.
		- Ej. Actualizaciones automáticas en sistemas operativos como Windows Update.
	- *Pull:* Los usuarios o administradores deben solicitar explícitamente las actualizaciones.
		- Ej. Descarga manual de parches y actualizaciones de seguridad en servidores Linux.
	- *Preguntas Clave*
		- ¿Cómo se entregan las actualizaciones a los usuarios?
		- ¿Qué método es más adecuado para nuestro sistema?

**Integración en el Sistema Existente: ¿Cómo el nuevo software o actualización se incorpora al *sistema existente y cómo se ejecuta?**
- *Aspectos de Integración*
	- *Integración en caliente:* Capacidad de integrar y ejecutar software mientras el sistema está en funcionamiento.
		- Ej. Servicios de microservicios donde cada componente puede actualizarse independientemente.
	- *Integración en frío:* Requiere detener el sistema antes de la integración.
		- Ej. Sistemas legado que necesitan reiniciar para aplicar actualizaciones
- *Preguntas clave:*
	- *Eficiencia:* ¿Qué tan rápido se puede desplegar e integrar el software?
	- *Controlabilidad:* ¿Cómo se puede controlar o revertir el despliegue si es necesario?

**Medio y empaquetado: Formato en que el software se empaqueta y el medio a través del cual *se entrega al host**
- *Medio de Entrega*
	- DVD, USB, entrega por Internet.
	- Consideraciones de ancho de banda, especialmente para sistemas móviles.
- *Empaquetamiento del Software*
	- Formatos: ejecutable, contenedor, plug-in.
- *Preguntas Clave*
	- ¿Cuál es el medio más efectivo para nuestro entorno?
	- ¿El empaquetado actual maximiza la compatibilidad y la facilidad de uso?

**Eficiencia y Control de Proceso de Despliegue**
- *Factores de Eficiencia:*
	- *Uso de Recursos:* Minimizar el impacto en la CPU, memoria y almacenamiento.
	- Ej. Sistemas que utilizan tecnologías como Kubernetes para escalar automáticamente según demanda.
	- *Tiempo de Despliegue:* Reducir el tiempo necesario para que la actualización esté lista para el uso.
	- Ej. Uso de pipelines CI/CD optimizados para automatizar pruebas y despliegues.
- *Preguntas Clave*
	- ¿Cuánto tiempo y recursos se requieren para completar el despliegue?
	- ¿Se maximiza la eficiencia del proceso?

**Control de Proceso de despliegue: Capacidad para controlar y revertir el despliegue si es necesario**
- *Elementos de Control:*
	- *Versionado:* Gestión de diferentes versiones del software durante y después del despliegue.
	- Ej. Uso de Git para gestionar cambios y controlar el despliegue de versiones específicas.
- *Acceso Controlado:* Restricciones de quién puede desplegar y qué puede ser desplegado.
	- Ej. Implementación de políticas de seguridad 