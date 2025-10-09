
El modelo cliente servidor.

- Se supone que el modelo osi, es una buena forma de organizar la informacion, ya que cuando un emisor envia in mensaje, se realiza un *entubamiento de bits* 
- La idea principal del modelo cliente/servidor es ver a un sistema como un conjunto de procesos llamados *servidore*, que ofrecen sus servicios a los usuarios llamados, *clientes*
- Una maquina puede ejecutar varios procesos a la vez y tambien varios clientes, asi como varios servidores o la combinacion de ambos.

**Ventajas del modelo cliente servidor

- **Sencillez** El cliente envia un mensaje y se obtiene una respuesta por parte del servidor
- No se tiene que establecer una conexion sino hasta que esta se utilice
- **La eficiencia** La idea basica del modelo, es que no se ocupen todas las capas como en el modelo osi. de tal forma que solo se definen 3 capas
	- la fisica
	- la enlace
	- la solicitud

Request -> response = cliente -> servidor
Solicit -> Response = servidor -> cliente

one way -> le digo que haga algo, sigo con mis cosas pero espero la respuesta

notification -> el servidor manda una notificacion

- Debido a su sencillez, teoricamente el modelo se implementa mediante 2 llamadas al sistema:
	- Para el envio de mensajes **send(dest,&mptr)
	- Para la recepcion de menesajes **recive(addr,&mptr)


**Direccionamiento**
- Antes de que un cliente pueda enviar un mensaje a algun servidor, necesita tomar en cuanta algunos aspectos como

- Integrar machine.numbre al codigo del proceso cliente donde:
	- machine: indica el numero de maquina dentro de red
	- number: el numero del proceso dentro de esa maquina

- *Desventajas*
	- ESte metodo no posee la tranparencia que se busca ya que se esta identificando que existen varias maquinas trabajando
	- Si el *servidor* falla, se pierde el servicio pues los programas compilados tienen integrado ese numero de maquina para ese servicio. Una variacion de este esquema, utiliza *machine.local_id*

**Dejar que los procesos elijan direcciones al azar y localizarlos mediante transmisiones**

- En una LAN aque soporte transmisiones, el emisor puede transmitir un paquete especial de localizacion con la direccion del proceso destino.
- Las maquinas en la red reciben este mensaje y verifican si la direccion es suya; en caso de que lo sea, regresa un mensaje äqui estoy" con su direccion en la red
- El cliente utiliza entonces esa direccion y la captura para uso posterior. SI bien esto cumple con las premisas, generea una carga adicional en el sistema


**Utilizar un hardware especial**

- En vez de localizar un proceso mediante transimisiones en toda la red, los chips de interface de la red se diseñan de modo que permitan almacenar direcciones de procesos para ellos
- Las trasmas usan direcciones de procesos en vez de direcciones de maquinas. Al recibir cada trama, el chip de interfase de las red solo tendria que examinar la trama para saber si el proceso destino se encuentra en esa maquina. En caso afirmativo, la aceptaria, de lo contrario no 


**Primitivas con bloqueo y sin bloqueo
- Las primitivas descritas anteriormente , reciben el nombre con bloqueo (sincronas) y sin bloqueo (asincronas)

**Primiticas con send con bloqueo**

- Mientras que se envia el mensaje el proceso emisor se bloquea.
- En algunos casos el receptor puede especificar de quienes quiere recibir el mensaje y queda bloqueado hasta que reciba el mensaje de el.
- En este tiempo, el CPU inactivo, desperdiciando tiempo.

**Primitivas send sin bloqueo (asincronas)
- El control se regresa de inmediato al emisor antes de enviar el msg.
- Se permite el trabajo en paralelo
- El mensaje es depositado en un buffer.

**Desventajas**
- El cliente no puede utilizar el buffer mientras el mesnaje se envia.
- El cliente no sabe a ciencia cierta cuando ah respondido el servidor

**Solucion**
Que el nucleo haga copias en un espacio privado, aunque de esta forma se desperdicia tiempo mientras se realiza la copia.

**Primitica confibale vz no confiable**

- Decimos que el mensaje es confiable cuando sabemos a ciencia cierta que este fue entregado.
- Un mensaje no es confiable, cuando no llega a su destino, existen 3 formas de pensar o de concebir este problema

 