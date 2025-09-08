### Objetivo

Mostrar la **vista física del sistema**, visualizando cómo el software es asignado y operado en hardware específico y cómo se da la comunicación entre los elementos.

---

### Vista Física

Enfocada en los **elementos físicos** del sistema.

---

### ¿Cuándo se usan diagramas de despliegue?

1. Especificar el **despliegue de artefactos**.  
2. Especificar la **localización de las entidades en tiempo de ejecución**.  

- Proporcionan una perspectiva del sistema en el **mundo real**, integrando hardware y software.  
- Los elementos del software se manifiestan como **artefactos**.  

---

### Artefactos

Un **artefacto** es un clasificador que representa una entidad física: una pieza de información que se utiliza o se produce mediante un proceso de desarrollo de software o mediante la implementación y operación de un sistema.  

**Ejemplos**:  
- Archivos ejecutables  
- Archivos de biblioteca  
- Archivos fuente  
- Archivos de configuración usados por el software  

**Representación**:  
- Un **rectángulo** en un diagrama de despliegue representa un artefacto.  

---

### Nodo

**Definición**: Un **nodo** es un recurso computacional disponible durante la ejecución, en el que los artefactos son desplegados para su uso.  

**Ejemplos**:  
- **Hardware**: cliente de escritorio, impresora (*estereotipo device*)  
- **Entornos de ejecución**: sistemas operativos, contenedor (*estereotipo execution environment*)  

Regularmente, un *device* contiene un **ambiente de ejecución**.  

**Representación**:  
- Un **cubo con el nombre del nodo**.  

---

### Nodo Clase

Tradicionalmente se refiere a **computadores de una red**, y es un tipo de recurso de cómputo disponible.  

- En él se ejecuta el componente de la interfaz de usuario.  

---

### Nodo Instancia

Un **nodo instancia** es un nodo específico de una clase, etiquetado con el nombre de la instancia y la clase.  

- Ejemplo: utilizado por *Jonathan* para acceder.  



## Caminos de comunicación

**Definición** Es una *Asociación* que representa la comunicación genérica entre nodos, permitiendo el intercambio de señales y mensajes

**Representación** Se muestran como lineas solidas entre nodos, sin indicar navegabilidad, asumiendo comunicación bidireccional 

- En entornos físicos, representa *Conexiones físicas*
- En entornos de ejecucion representan *Protocolos* específicosq
