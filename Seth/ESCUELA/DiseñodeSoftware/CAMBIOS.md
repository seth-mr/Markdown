# ¿POR QUÉ CAMBIA EL SOFTWARE?

El software cambia por distintas razones: funcionalidades, tecnologías, regulaciones, mantenimiento, capacidad y escalabilidad.

---

## EN QUÉ PUEDE CAMBIAR

- **Funcionalidades**: adquisición, eliminación o modificación de las funcionalidades que el sistema ofrece.
    
- **Tecnologías**: mejoras en la eficiencia.
    
- **Regulatoria**: ajustes para cumplir con nuevas normativas.
    
- **Mantenimiento**: corrección de errores y adaptaciones a nuevas plataformas o tecnologías.
    
- **Capacidad y escalabilidad**: ajustes para soportar mayor carga o mejorar rendimiento.
    

---

## COSTO DEL CAMBIO

No es posible diseñar para todos los atributos, por lo que se deben considerar varios factores:

- **Altos costos**: incrementa el costo del desarrollo.
    
- **Problemas de calidad**: podría comprometer otras dimensiones.
    
- **Priorizar cambios probables**
    

### Costo-Beneficio

- **Selección del soporte**: decidir qué herramientas o mecanismos facilitarán futuros cambios.
    
- **Introducción del mecanismo**: costo asociado con implementar mecanismos que faciliten cambios futuros.
    
- **Relación de las modificaciones**: costo de realizar un cambio usando los mecanismos introducidos.
    

#### Cambio simple (cambiar la fuente o un bug)

- **Mecanismo**: cambiar el código fuente directamente tras recibir una solicitud.
    
- **Costos**:
    
    - _Introducción_ → Ninguno (no se introduce un mecanismo especial)
        
    - _Realización_ → Costo de modificar el código y revalidar el sistema
        

#### Cambio complejo (generados de apps)

- **Mecanismo**: uso de herramientas que generan código complejo basado en aplicaciones, pruebas e implementación de UI
    
- **Costos**:
    
    - _Introducción_ → Alto, debido a la adquisición de la herramienta
        
    - _Realización_ → Bajo
        

---

## QUÉ PUEDE CAMBIAR

- Las _funciones_ que el sistema realiza
    
- La _plataforma_: hardware, sistema operativo o middleware
    
- El _entorno_: sistemas con los que debe interoperar, protocolos de comunicación
    
- Las _cualidades_ del sistema: desempeño, confiabilidad, futuras modificaciones y capacidad
    

---

## JUSTIFICACIÓN DEL CAMBIO

- **Considerar el costo-oportunidad**: los recursos podrían destinarse mejor en otras áreas
    
- **Evaluar el impacto temporal**: a veces un mecanismo a largo plazo es mejor, pero los plazos pueden limitar la opción
    
- **Evitar deuda técnica**: cambios continuos sin mecanismos adecuados pueden acumular deuda técnica
    

---

## EJEMPLOS

- **Funcionales**: añadir una nueva funcionalidad de búsqueda avanzada en una aplicación de comercio
    
    - Requiere ajustes en la interfaz, la lógica y la base de datos
        
- **Mantenimiento**: optimización de un sistema de gestión de inventario para mejorar la eficiencia
    
    - Implica reescritura de consultas SQL para reducir los tiempos de respuesta
        
- **Capacidad y escalabilidad**: escalar una aplicación web para manejar 10 veces más tráfico
    
    - Implica la adición de más servidores al clúster
        

---

## FACTORES DE CAMBIO

- **Qué puede cambiar** y **qué tan probable es**
    
- **Quién y cuándo realiza el cambio**: desarrolladores, usuarios finales o el sistema mismo
    
- **Costo del cambio**: recursos necesarios para implementar y facilitar los cambios, y recursos para realizar los cambios
    

### Cuándo se realizan los cambios

- **En la implantación**: modificación directa del código, normalmente urgente
    
- **Durante la construcción**: uso de sándwiches durante la… _(nota: incompleto)_
    
- **En la configuración**
    
- **Durante la ejecución**

### Evaluar el costo de los cambios 

N x el costo del cambio sin el mecanismo >= Costo de crear el mecanismo + (N x Costo de hacer el cambio con el mecanismo)

N x el costo de hacer el cambio usando el mecanismo 

N = numero anticipado de modificaciones usando el mecanismo

Costo de hacer el cambio sin el mecanismo 
Costo de crear el mecanismo 
Costo de hacer el cambio usando el mecanismo