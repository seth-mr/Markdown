- Las arquitecturas existen para *satisfacer las necesidades de los stakeholders*
- Una *buena arquitectura* atiende a sus concerns y equilibra conflictos aceptablemente

**AD** Conjunto de productos que se comunican la arquitectura y demuestran que atienden los concerns, No basta con "tener" Arquitectura es necesario poder *comunicar la arquitectura*
ce forma clara

- Es imposible capturar toda la funcionalidad y todas las cualidades de un sistema complejo en un modelo comprensible
- Se describe mejor con un *conjunto de vistas* que, en conjunto muestran que se cumplen los objetivos.

**Vista** representación de aspectos estructurales que muestra como la arquitectura atiende ciertos concerns para ciertos stakeholders

**Regla de oro** Incluye en cada vista solo lo que ayuda a explicar la arquitectura o a demostrar el cumplimiento de objetivos

**View Point** patrones/plantillas/convenios para construir para cada tipo de vista: define stakeholders, concerns y lineamientos.

**Perspectiva arquitectónica** actividades, tácticas y guías para asegurar un conjunto de atributos de calidad a través de varias vistas

**Táctica** un enfoque probado para mejorar un atributo de calidad

### ASR
 **Requisito arquitectonico significativos**

- Puede ser de calidad o funcional
- es un concern que impacta amplia mente la estructura o cualidades clave


### Modelo de tres picos
- **Requisitos** proporcionan el contexto: alcance, funcionalidad y cualidades deseadas
- **Definición de arquitectura** revela omisiones/inconsistencias y costes; realimenta a requisitos
- **Construcción** Se planifica en incrementos; valida/retroalimenta la arquitectura durante todo el ciclo

### Esquema minimo de AD

1. **Introducción y alcanza**:
	1. Contexto del sistema y objetivos del negocio
2. **Rescolderas y concern**
	1. tabla clara de interesados y sus preocupaciones
3. **Principios arquitectonicos**
	1. decisiones que guían el diseño
4. **Vistas**
	1. Stake holders y concerns
	2. Viewpoint
	3. Objetivo de la vista
	4. Elementos y relaciones
	5. Evidencia
	6. Notas de consistencia
5. **Perspectivas**
	1. Tacticas usadas y su proyección en varias vistas
6. **ASR**
	1. lista y trazabilidad a vistas/ decisiones
7. **Decisiones de diseño**
	1. Decisiones clave y su justificación frente a concerns en conflicto

