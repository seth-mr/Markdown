*Diseño*
- **Disciplina:** Aplicación de conocimiento, información e imaginación para definir un sistema que cumpla funciones específicas con máxima eficiencia.
- **Procesos:** Procedimientos que se realizan dentro de esa disciplina.
- **Resultados:** El producto final resultante de aplicar la disciplina de diseño.
- **Etapa del ciclo de vida:** Fase en la que los procesos de diseño producen los resultados esperados.

¿Qué implica diseñar?
1. Satisfacer *necesidades* de los involucrados
2. Cumplir con *presupuestos* y *plazos*
3. Manejar *restricciones*
4. Trabajar con los *recursos disponibles*

**Restricción:** Regla de negocio que alguien ya tomó por nosotros

El diseño de Software se realiza en tres etapas
1. *Diseño Arquitectónico:*
	- Diseño de la arquitectura general del sistema de software.
2. *Diseño de Alto Nivel:*
	- Diseño orientado externamente del sistema y sus componentes.
3. *Diseño Detallado:*
	- Diseño interno, con un enfoque en los detalles que permiten la construcción del sistema.

## ¿Qué es la Arquitectura de Software?
"La arquitectura de software es el conjunto de estructuras necesarias para razonar sobre el sistema, que incluyen elementos de software, relaciones entre ellos y sus propiedades"

Bass et al. (2021)

Importancia de la Arquitectura
- Puente entre objetivos del negocio y el sistema final.
- Permite analizar y documentar decisiones de diseño.
- Impacta directamente en atributos de calidad.
- Existen muchas propiedades de calidad posibles en un sistema.

En este curso nos centraremos en:
- Availability -> Disponibilidad
	- Capacidad del sistema de estar operativo cuando se necesita, incluso frente a fallos.
- Deployability -> Facilidad de despliegue
	- Qué tan sencillo y rápido es poner nuevas versiones en producción sin interrumpir el servicio.
- Energy efficiency -> Eficiencia energética
	- Uso óptimo de recursos energéticos por parte del software y la infraestructura.
- Integrability -> Facilidad de intregración
	- Qué tan fácil es integrar el sistema con otros sistemas, APIs o plataformas externas.
- Modifiability -> Facilidad de modificación
	- Qué tan fácil es realizar cambios en el sistema (funcionalidades, correcciones, mejoras) sin introducir errores.
- Performance -> Rendimiento o Desempeño
	- Capacidad de responder dentro de tiempos aceptables bajo distintas cargas.
- Safety ->  Protección
	- Capacidad del sistema de evitar condiciones peligrosas o daños físicos al entorno o a las personas.
- Security -> Seguridad (ciberseguridad)
	- Protección frente a accesos no autorizados, modificaciones indebidas y ataques.
- Testability -> Facilidad de prueba
	- Qué tan fácil es diseñar y ejecutar pruebas para verificar el funcionamiento del sistema.

*Arquitectura y Mantenimiento*
- La arquitectura no solo organiza, también facilita o dificulta el mantenimiento.
- Sistemas como *mala arquitectura:* cambios costosos, deuda técnica, riesgos en operación.
- Sistemas con *buena arquitectura:* adaptables, escalables, resistentes a fallas.
Definición contemporanea de deuda técnica

Arquitectura vs Diseño
- Arquitectura = Decisiones de alto nivel que permiten razonar sobre el sistema (estructuras, relaciones, propiedades).
- Diseño detallado = Decisiones locales, implementaciones específicas

# Deuda Técnica
1. Se refiere a los costos futuros asociados con confiar en atajos o decisiones subóptimas durante el *desarrollo de software*. También llamados deuda de código o deuda de diseño, estos compromisos se deben principalmente a arreglos rápidos, documentación deficiente y dependencia de código obsoleto. Con el tiempo, esta deuda debe abordarse, lo que requiere un esfuerzo adicional. 
   https://www.ibm.com/mx-es/think/topics/technical-debt

## Causas de la deuda técnica
1. *Definición inicial insuficiente*, donde los requisitos todavía se están definiendo durante el desarrollo, el desarrollo comienza antes de que se lleve acabo cualquier diseño.
2. *Las presiones comerciales*, donde la empresa considera que se publique algo antes de que se completen los cambios necesarios.
3. *Falta de proceso o comprensión*, donde las empresas son ciegas al concepto de deuda técnica y toman decisiones sin considerar las implicaciones.
4. *Componentes estrechamente acoplados*, donde las funciones no son modulares, provocando que el software no sea lo suficiente flexible como para adaptarse a los cambios de las necesidades comerciales.
5. *La falta de un conjunto de pruebas*, que fomenta la reparación rápida de errores.
6. *Falta de documentación*, donde el código se crea sin documentación de respaldo. 
7. *Falta de alineación con los estándares*
8. *Pobre liderazgo tecnológico*
9. *Cambios de especificación de última hora*
https://es.wikipedia.org/wiki/Deuda_t%C3%A9cnica#cite_note-Jeffries_2015-4
