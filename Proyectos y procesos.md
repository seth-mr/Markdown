# Flujo de Requisitos y Especificación

## Flujo de trabajo de requisitos
- Genera un **modelo de concepto de negocio** y un **modelo de caso de uso**.  
- La salida es el **modelo de conceptos de negocio**, que enumera los conceptos importantes del dominio/problema y muestra sus relaciones.  
- Los **casos de uso** aclaran:
  - El límite del software.  
  - Los actores.  
  - Cómo interactúan con el sistema.  

  Los artefactos se refinan en los siguientes flujos:  
	- ¿Qué información necesita ser manejada por el sistema?  
	- ¿Qué interfaces necesito para trabajar la información?  
	- ¿Qué componentes deben proveer esa funcionalidad?  
	- ¿Cómo van a encajar esos componentes?  

### Capas del sistema
- **Capa de servicios del sistema**  
- **Capa de servicios del negocio**

---

## Flujo de trabajo de especificación
Se divide en **tres etapas**:

### 1. Identificación de componentes
- **Objetivo:** crear un conjunto inicial de interfaces y especificaciones de componentes.  
- **Entrada:** modelo de concepto de negocio y modelo de casos de uso.  
- **Salida:** **Modelo de tipos de negocio** (artefacto de especificación importante).  

---

### 2 Identificación de interfaces del sistema
El diálogo implementa una interacción entre el **actor** y el **sistema**.  
Se estudia cómo es la interacción para identificar la lógica de casos de uso que lleva a la definición de interfaces.

### Reglas
1. En cada paso, el sistema debe proporcionar **0, 1 o N operaciones** para mapear sus responsabilidades.  
2. No es un **mapeo uno a uno**.  

Las **interfaces del sistema** y sus operaciones iniciales **emergen del modelo de casos de uso**.  
Estas especificaciones detallan cómo los usuarios y sistemas externos interactúan.  

 Recordar: la propuesta se centra en el **lado del servidor**.  

---

## Ejecución en tiempo de ejecución
1. El usuario inicia un **caso de uso** y la lógica crea/muestra la **GUI** adecuada.  
2. El usuario es guiado a través del caso de uso por su lógica.  
3. Siempre que la lógica del CU necesita información para mostrar o notificar al sistema de una acción del usuario, llama a la **operación apropiada** en la lógica del paso del CU.  
4. Esa operación utiliza las **operaciones de la lógica de negocio** para realizar su función.  


### 3 identificacion de interfaces del negocio

## Modelo de conceptos de negocio

El modelo de conceptos de negocio es una vision del mundo pero desde el sistema.

nos centra en la informacion y procesos que el sistema gestiona.

El modelo de sistemas del negocio es una refinacion

Se utiliza para desarrollar las interfaces del negocio

vision del mundo -> punto de vista del sistema

Las operaciones de componentes realizan su trabajo invocando operaciones de interfaces del negocio

EL modelo de tipos de negocio coconiene informacion especifica que el sistema necesita

Identificar los tipos de neogocios principales

Crear interfaces de negocio para los tipos principales y agregarlas al modelo

Refinar el modelo para indicar las responsabildidades de la interfaz de negocio


# Reglas de negocio

Es importante tener un bussines type model preciso 
las reglas de negocio proporcionan una base precisa sobre la cual trabajar

