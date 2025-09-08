## Agenda
#### Necesidad de probar
- Relación con requisitos
- Importancia
- Defectos y su inyección
- Causas de los defectos
#### Definición de prueba
- Definición
- Proceso de prueba
- Objetivos de la prueba
#### Conceptos relacionados
- Error, defecto y fallo
- Amplificación de defectos
- Revisiones y prueba

## Desarrollo de software
Se pueden cometer errores o tener omisiones

Necesidades -> Requisitos -> Análisis -> Diseño -> Construcción -> **Prueba**

**Necesidades:** De negocio, operativas y funcionales
**Requisitos:** Funcionales y no funcionales
**Diseño:** De arquitectura y software
**Pruebas:** Constata el cumplimiento de los requisitos funcionales y no funcionales
**Construcción:** De software

En cualquier fase se pueden cometer errores o tener omisiones

Las necesidades de transforman en un software que las resuelva
## Importancia de los requisitos en la prueba
- **Funcionales:** Funciones que el sistema deberá ser capaz de realizar (transformaciones que realiza sobre entradas para producir las salidas deseadas)
- **No funcionales: Características que de una u otra forma pueden limitar el sistema
- Definen lo que el sistema debe ser, por lo que son la base más importante de contraste en las pruebas (**NO SON LA ÚNICA BASE**)
# Calidad de un requisito
- **Necesario:** Si su omisión provoca una **deficiencia en el sistema a construir** y además su capacidad, características físicas o factor de calidad que NO pueden ser reemplazadas
- **Conciso:** Si es fácil de leer y entender. Su redacción debe ser simple y clara para aquellos que vayan a consultarlo en un futuro
- **Completo:** Si no necesita ampliar detalles
- **Verificable:** Cuando puede ser cuantificado de manera que permita hacer uso de los siguientes métodos de verificación: inspección, análisis, demostración o pruebas
## Por qué es necesario probar
Para verificar que se están cumpliendo las expectativas de los Stakeholders y garantizar un producto y trabajo de calidad profesional: Ausencia de DEFECTOS
La probabilidad de que haya un error **jamás** será **0**, probamos para reducir esa probabilidad
## Defecto de un software
Los defectos del software (conocidos en el argot de los desarrolladores como Bug), corresponden a un error, imperfecto o falla de una aplicación para computador que puede causar un **resultado no deseado o incumplimiento de un requerimiento**
**Los defectos en el software se pueden inyectar en cualquier etapa del desarrollo**
## Qué causa un defecto
1. Mala comunicación con el cliente
2. Definición incorrecta o ausencia de los requisitos
3. Errores de diseño
4. Errores de codificación
5. Incumplimiento de estándares
6. Pruebas insuficientes
7. Errores de documentación
## Inyección de defectos
- La mayor parte de los defectos se inyectan en las etapas tempranas del proceso de desarrollo
	- Requisitos = 56%
	- Diseño = 27%
	- Codificación = 7%
	- Otros = 10%
- Entre más tarde se descubra el error es más caro
- Etapa de detección de defectos
	- Requisitos y diseño = 4%
	- Construcción y pruebas unitarias
	- Pruebas de aceptación
## ¿Cero defectos?
- No es posible generar un producto con **0 defectos**
- Sí es posible con una mejora en procesos, producir software con pocos defectos o con una tasa de defectos controlada
# Definición de prueba
Las pruebas de Software consisten en verificar el comportamiento de un programa dinámicamente a través de un grupo finito de casos de prueba, debidamente seleccionados del, típicamente, ámbito de ejecuciones infinito, en relación al comportamiento esperado. IEEE
Ejercitar un programa + Proceso + Encontrar defectos = Prueba de Software
# Reflexión
- ¿Qué mide una prueba?
	- Mi producto y mi proceso, qué tan bien está el programa y qué tan bien está hecho
- ¿Qué demuestra una prueba?
	En qué están fallando los procesos de desarrollo, no solo los bugs
- ¿Qué permite predecir una prueba?
	Cuántos defectos se le van al cliente
No puedes esperar resultados diferentes si sigues haciendo lo mismo, los resultados de las pruebas nos muestran en qué estamos fallando y con esos resultados debemos mejorar en cada proyecto
# Conclusión
- Las pruebas funcionan sólo en un rango y ambiente limitado
- Las pruebas decisivas son difíciles de escribir
	- Hay que saber qué pruebas hay que hacer y cuáles se van a automatizar
- Siempre hay personas que creen que sí pueden ser concluyentes las pruebas a pesar de la evidencia
- Se debe evaluar la prueba que será aplicada antes de usarse
- Emitir los resultados falsos de una prueba, puede ser aceptada socialmente **pero destruye la reputación**