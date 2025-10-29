## 1. Nombre o estilo del patrón arquitectónico
Model-View-Controller (MVC)
## 2. Descripción
- Divide una aplicaión interactiva en tres componentes:
	- Modelo: Contiene la funcionalidad e información del núcleo
	- Vista: Muestra la información al usuario
	- Controladores: Manejan la entreada del usuario
- La vista y los controladores comprenden la interfaz del usuario
- Un mecanismo de propagación de cambios asegura la consistencia entre la interfaz de usuario y el modelo
### a) Contexto
- Aplicaciones interactivas con una interfaz humano-computadora flexible
### b) Problema
-  Las interfaces de usuario son propensas a cambiar solicitudes. Cuando se extiende una funcionalidad de la apilcación se deben modificar menús para acceder a estas nuevas funciones. De este modo la plataforma de interfaces de usuario de sistemas longevos representan un objetivo móvil y cambiante.
- El soporte para paradigmas de interfaz de usuario deben ser fácilmente incorporables
- Construir un sistema con la flexibilidad requerida es caro y tiende a errores si la interfaz de usuario está entretejida con la funcionalidad del núcleo, esto genera alto acoplamiento.
### c) Descripción de la solución
- Se introdujo por primeravez en la Smalltalk-80 programming environment [KP88].
- MVC Divide una aplicación interactiva en tres áreas: proceso, salida y entrada
- El componente *modelo* encapsula la información y funcionalidad principal. Es indepenfiente de representaciones de salida específicas o comportamiento de entradas
- El componente *vista* muestra la información al usuario
- Una *vista* obtiene la información del *modelo*
- Cada *vista* tiene un componente *controlador* asociado.
- Los *controladores* reciben la entrada, usualmente eventos como movimientos de mouse, interacción con botones o entradas del teclado
	- Los eventos son traducidos a solicitudes de servicio para el *modelo* o la *vista*
	- El usuario interactúa con el sistema únicamente mediante los *controladores*
- La separación del modelo entre *vista* y *controlador* permite múlitples *vistas* del mismo modelo. Si el usuario cambia el *modelo* desde *controlador* de una *vista* todas las vistas dependientes de esa información deben reflejar los cambios
### d) Fuerzas actuando
- Descripción de los elementos
	- Relaciones entre esos elementos
Ventajas
Desventajas
Cuando usar ese patrón
aplicaciones reales de ese patrón
Diagrama e ilustraciones del patrón
Herramientas y tecnologías asociadas con ese patrón

Fuentes
- El del pájaro (Richards y Fords)
- Pattern oriented software arch