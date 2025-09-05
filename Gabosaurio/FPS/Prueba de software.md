## Supuestos
- La prueba de software, supone su ejecución para identificar errores
- Una prueba no puede ser efectiva, si no considera la complejidad del software
- Diseñar pruebas, requiere resolver problemas similares los encontrados a nivel de análisis, diseño y programación de una aplicación
## Qué implica una prueba
- En el ejemplo observamos que al menos tenemos tres casos de prueba:
	1. Dar valores iguales a N1 y a N2
	2. Dar valores donde N1 sea mayor a N2
	3. Dar valores donde N2 sea mayor a N1

	**Ejercicio**
		INICIO
		Leer n1, n2
		SI N1 = N2 ENTONCES
			ESCRIBIR ("Son iguales")
		SINO
			SI N1 > N2 ENTONCES
				ESCRIBIR ("N1 es el mayor)
			SINO
				ESCRIBIR ("N2 es el mayor)
		FIN
		
	- ¿Qué errores faltan por probar?
		- Validar que las entradas sean números
## Casos de prueba
- Identificar, modelar y analizar las responsabilidades del sistema bajo prueba
- El diseño de casos de prueba basados en la perspectiva o punto de vista externo al sistema
- Adicionar casos de prueba basados en el análisis del código, suposiciones y heurísiticas
	- Jugar con las condiciones
- Desarrollar los resultados esperados para cada caso de prueba y un esquema de evaluación que indique si la prueba fue "pasada" o no y en qué estado se encuentra el caso de prueba
## Visión general de la prueba}
- Modelado de la aplicación de pruebas
	- Qué y cómo probaré
- Aplicación de prueba
	- No se hacen forzosamente las mismas pruebas que en la iteración pasada
	- Debemos corregir los casos de prueba
## Pasos típicos de una prueba
- Establecer alcance y diseñar
- Ejecutar prueba y evaluar resultados
- Evaluar cobertura de la prueba
- Pruebas adicionales para alcanzar cobertura
- Detener cuando la cobertura es la esperada y todas las pruebas pasan
### Cobertura de prueba
- Grado en el que el código fuente de un programa ha sido comprobado
- También para la IA hay cobertura (se debe probar todo programa con IA)
## Garantía de calidad
La gestión de calidad es el conjunto de acciones planificadas y sistemáticas, necesarias para dar la confianza adecuada de que un producto o servicio va a satisfacer los requisitos de calidad.
Siempre se debe dar una garantía, es un requisito legal.
El plazo mínimo-recomendado es de un mes o dos meses, ya que los cierren de muchos sistemas son mensuales entonces da tiempo de ver si un sistema funcionó. Otros son anuales.
La gestión de calidad es una actividad de "Protección" que se encuentra a lo largo del proceso de software
### SQA Para el software
**SQA - System Quality Assurance (Sistema de Gestión de Calidad)**
Abarca:
1. Un proceso de garantía de calidad de software
2. Tareas específicas de asegurameinto y control de calidad
### Búsqueda de calidad
- En el software se busca minimizar el número de defectos que se liberan en una versión. Tener los menos defectos posibles
- Y también minimizar la varianza en el número de bugs de una liberación a otra. Que una versión posterior tenga menos que la inicial
## Calidad de software
Concordancia:
- Requisitos funcionales
- Requisitos de desempeño explicitados
- Estándares de desarrollo documentados
- Características implícitas de un trabajo profesional
## Resúmen
- La PRUEBA es parte de la Garantía de Calidad, que pretende la SATISFACCIÓN DEL CLIENTE
- "Cuesta 6 veces más conseguir un nuevo cliente que mantener a uno satisfecho"
## Limitaciones
1. Nivel de "correctez"
	- "La prueba de un programa puede servir para mostrar la presencia de defectos, pero nunca la ausencia de ellos" - Dijkstra
2. Grado de automatización
	- Automatizar ciertos aspectos del diseño de pruebas es probablemente imposible
	- El beneficio de automatizar es la aplicación y la reaplicación de las pruebas, es una inversión a largo plazo.
3. Dependencia de la especificación
	- La prueba usa como putnod ereferencia los requerimientos y demás especificaciones de ingeniería y éstos pueden ser incorrectos
4. Error humano