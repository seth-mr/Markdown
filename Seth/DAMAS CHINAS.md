w
## Historia

las "Damas chinas" nombre con el que se les conoce actualmente es un juego con origen ruso nacido en 1982 con el nombre de Stern-Halma (Stern es estrella en ruso) ya que es una variante de un juego estadounidense llamado Halma.
--ual del juego se origino en estados unidos como una estrategia de marketing.


## Elementos del juego

# Tablero 

![[Pasted image 20250827125102.png|446x431]]
- Tradicionalmente consta de *121 casillas circulares* cuya forma es dada para contener las fichas del juego que por lo regular son canicas.

- Este tiene forma de  hexagrama regular coloquial mente conocido como  *estrella de david* (de 6 puntas)


- Es muy practico decir que el tablero consta de dos partes que gozan de distinta intención, las puntas de la estrella que por simplicidad referiremos en este documento como *"puntas"* y el hexágono central de la estrella al que nos referiremos como *" centro"* , 


las puntas puede verse como una estelación compuesta de 6 triángulos equilátero hacia arriba (azul aquí) y hacia abajo (rosa), cuya interseccion forma el centro, un  hexagono regular (verde)

### Puntas

- Cada uno de los 6 triángulos que conforman el grupo al que hemos denominado puntas esta tradicionalmente compuesto por 10 casillas para colocar fichas mismas que tienen una distribucion de *Triangulo equilatero* con base 4.

![[Pasted image 20250827123609.png]]

 - Cada punta debe *asociarse con un color* que no debe repetirse en otra punta y todas las casillas contenidas en un punta son coloreadas del tono correspondiente a su punta.


### Centro 

-  el centro consta de *61 casillas* de color blanco 

- Cada una de estas casillas limita con las seis contiguas (salvo las situadas en los bordes del tablero, que limitan con dos, cuatro o cinco)


### Fichas
- Estas tradicionalmente tienen forma de canicas y encajan en las casillas del tablero.

- La cantidad de fichas que se utilizaran para jugar al juego esta determinada por la cantidad de jugadores existiendo las siguientes opciones.

	- 2 jugadores = 20 fichas
	- 4 jugadores = 40 fichas 
	- 6 jugadores = 60 fichas

- El color  las fichas de cada jugador debe coincidir con el color de la punta elegida por cada jugadores.


## Reglas del juego

### Objetivo

- El objetivo de cada jugador es **trasladar todas sus fichas desde la punta de inicio hasta la punta opuesta** del tablero.
    
- Gana el primer jugador que logre **ocupar completamente la punta opuesta** con todas sus fichas.
    

---

### Número de jugadores

- El juego *únicamente puede jugarse con múltiplos de 2 jugadores*.
    
- Las configuraciones válidas son:
    
    - **2 jugadores**
        
    - **4 jugadores**
        
    - **6 jugadores**
        
- En cada configuración:
    
    - Los jugadores deben ocupar puntas *simétricamente opuestas* para garantizar equilibrio.
        
    - En caso de 4 jugadores, se dejan libres dos puntas opuestas entre sí.
        

---

### Disposición inicial

- Cada jugador debe elegir una punta de la estrella como su zona inicial.
    
- Se colocan todas sus fichas en las *10 casillas* de esa punta, de acuerdo con la distribución triangular de base 4.
    
- El color de las fichas debe coincidir con el color de la punta elegida.
    
- Las puntas opuestas son las metas de cada jugador.
    

---

### Turnos

- El juego se desarrolla por *turnos* en sentido horario.
    
- En cada turno, un jugador puede realizar *una de las siguientes acciones* con una de sus fichas:
    
    1. **Movimiento simple**: mover la ficha a una casilla vacía adyacente.
        
    2. **Movimiento de salto**: mover la ficha saltando sobre una ficha contigua (propia o rival) hacia la primera casilla libre inmediatamente después.
        

---

### Movimiento de salto

![[Pasted image 20250827132504.png]]


- El salto es válido siempre que:
    
    - La casilla inmediatamente adyacente contenga una ficha.
        
    - La casilla siguiente, en línea recta, esté libre.
        
- Se pueden encadenar saltos en un mismo turno, siempre que:
    
    - Todos los saltos sean consecutivos y legales.
        
    - Se realicen en direcciones rectas.
        
    - No se repita casilla en la misma secuencia de saltos.
        
- Una ficha puede saltar sobre fichas de cualquier color.
    

---

### Restricciones

- Una ficha no puede *retroceder a su propia punta de origen* una vez que ha salido completamente de ella.
    
- No está permitido *invadir la punta de un jugador rival*, salvo que esa sea su meta.
    
- Un jugador no puede mover más de una ficha por turno.
    

---

### Finalización de la partida

- La partida termina en cuanto un jugador *llena completamente su punta opuesta* con sus fichas.
    
- En partidas con más de dos jugadores:
    
    - El primer jugador en lograrlo gana.
        
    - Opcionalmente, se puede continuar para decidir el *segundo y tercer lugar*.


## Consideraciones para programar

### Jugadores

- Número permitido de jugadores: _2, 4 o 6_.
    
- Atributos mínimos:
    
    - `idJugador`
        
    - `nombre`
        
    - `color` → único dentro de la partida.
        
    - `puntaInicial`
        
    - `puntaMeta`
        
    - `fichas` → colección de 10 fichas asignadas.
        
- Validaciones:
    
    - No puede haber dos jugadores con el mismo color.
        
    - Las puntas elegidas deben estar en posiciones *simétricas*.
        

---

### Tablero

- Total de casillas: *121*.
    
- Estructura:
    
    - *6 puntas* → 10 casillas cada una (total 60).
        
    - *Centro* → 61 casillas.
        
- Cada casilla:
    
    - `idCasilla`
        
    - `tipo` → `"punta"` o `"centro"`
        
    - `color` →
        
        - Color de la punta (si pertenece a una).
            
        - Blanco (si es centro).
            
    - `adyacentes` → lista de casillas vecinas.
        
    - `ocupadaPor` → `idFicha` o `null`.
        

---

### Fichas

- Cada jugador controla *10 fichas*.
    
- Atributos:
    
    - `idFicha`
        
    - `jugadorId` (dueño)
        
    - `color` (heredado del jugador)
        
    - `posicionActual` (idCasilla)
        
    - `estado` → `"enJuego"` o `"enMeta"`.
        
**Regla clave**:
    
- *Las fichas conservan siempre el color de su jugador*, incluso después de salir de la punta inicial o moverse al centro/otra zona del tablero.
        
- Esto implica que el motor nunca debe “recolorear” fichas ni asignarlas a otro jugador.
        

---

### Configuración inicial

- *2 jugadores* → puntas opuestas.
    
- *4 jugadores* → se usan 4 puntas, dejando libres 2 opuestas.
    
- *6 jugadores*→ se ocupan todas las puntas.
    
- En todos los casos:
    
    - Cada punta seleccionada contiene exactamente 10 fichas del mismo color.
        
    - Las puntas libres permanecen vacías.
        

---

### Turnos

- Orden de turnos → *sentido horario*.
    
- `jugadorActivo` → cambia tras cada turno.
    
- Acciones permitidas:
    
    1. **Movimiento simple** → casilla adyacente vacía.
        
    2. **Movimiento de salto**→ sobre ficha contigua hacia casilla libre en línea recta.
        
- Un turno permite *mover una sola*, aunque se encadenen varios saltos.
    

---

### Movimientos

- **Movimiento simple**: casilla debe ser adyacente y vacía.
    
- **Movimiento de salto**:
    
    - Casilla intermedia ocupada por *cualquier ficha* (propia o rival).
        
    - Casilla destino vacía.
        
    - Salto en línea recta.
        
- **Saltos múltiples**:
    
    - Permitidos siempre que cada salto sea válido.
        
    - No se puede pasar por la misma casilla dos veces en la misma secuencia.
        

---

### Restricciones

- Una ficha no puede volver a la *punta inicial* si ya la abandonó completamente.
    
- No se puede ocupar la punta de otro jugador, salvo si es la *puntaMeta*.
    
- Una casilla no puede contener más de una ficha.
    
- Un jugador no puede mover más de una ficha por turno.
    

---

### Condiciones de victoria

- Gana el primer jugador en ocupar completamente su *puntaMeta* con sus 10 fichas.
    
- Definición:
    
    - Todas las casillas de la puntaMeta están ocupadas por las fichas del jugador.
        
    - Ninguna ficha de ese jugador se encuentra fuera de la puntaMeta.
        

---

### Estado de la partida

- Debe mantenerse en todo momento:
    
    - Lista de jugadores (con puntas y colores asignados).
        
    - Estado del tablero (ocupación de cada casilla).
        
    - Estado de fichas (posición y dueño).
        
    - Turno actual y jugador activo.
        
    - Opcional: historial de movimientos.
        

---

### Validaciones críticas

- Al inicio:
    
    - Número válido de jugadores.
        
    - Puntas ocupadas correctamente.
        
    - 10 fichas por jugador en su punta.
        
- En cada turno:
    
    - El movimiento propuesto es legal.
        
    - No se invade una punta indebida.
        
    - No se colocan dos fichas en la misma casilla.
        
- Al finalizar:
    
    - Verificar victoria según reglas exactas.

---

# Delimitación del Alcance del Proyecto

Este proyecto busca desarrollar una versión completa del juego Damas Chinas para múltiples jugadores, con conexión en red, registro de usuarios y una interfaz moderna. A continuación se detallan los elementos principales que estarán incluidos en el desarrollo.

## Requisitos Funcionales Básicos

- Movimiento de fichas (clic o teclado).
- Detección de movimientos válidos.
- Detección de ganador.
- Interfaz gráfica o de consola.
- Soporte para 2-6 jugadores.

---
## Versión del Juego

- Soporte para *2 a 6 jugadores*.
- *Juego multijugador por invitación* (por correo electrónico o código).
- Cada jugador puede ingresar con su cuenta o como invitado.
- Personalización visual y de reglas simples.

---

## Requisitos del Proyecto

### Etapas de desarrollo

- Definición de artefactos para cada etapa (análisis, diseño, implementación, pruebas).
- Registro de avance individual usando **GitHub

### Tecnologías y frameworks

- *Framework de persistencia: Uso de **Entity Framework* para enviar y recibir datos, y mapear objetos a la base de datos.
- *Framework de red: Uso de **WCF (Windows Communication Foundation)* para gestionar la comunicación entre clientes y el servidor.
- *Interfaz de usuario (UI): Desarrollo con **WPF (Windows Presentation Foundation)* para construir una interfaz visual atractiva.

### Seguridad

- Prácticas seguras al escribir código:
  - Pruebas contra inyecciones de datos.
  - Validación de mensajes y entradas.
  - Protección de la interfaz y conexión con el servidor.
- Seguridad en base de datos:
  - Activar *SQL Server Authentication*.
  - Crear una cuenta exclusiva para el acceso, con contraseña segura.
  - Restringir permisos solo a la base de datos del proyecto.
- Evitar el uso de *antipatrones* de programación.

### Idiomas

- Soporte automático para *español e inglés*.
  - El juego detectará el idioma del sistema operativo y cambiará automáticamente.

### Pruebas

- Por cada funcionalidad, se deben implementar al menos *5 pruebas* (unitarias, de integración o funcionales).

---

## Características Generales del Juego

### Cuentas y jugadores

- *Registro de usuarios/jugadores*:
  - Requiere confirmación por *correo electrónico*.
- *Cambio de contraseña*:
  - Contraseñas almacenadas de forma segura.
  - No requiere confirmación por correo (extra).
- *Personalización de perfil*:
  - Avatar, apodo (nickname), nombre, apellidos, correo y redes sociales.
- *Consulta de estadisticas basicas*
	- Consultar la cantidad de partidas jugadas, ganadas y perdidad.

### Modos de juego

- *Inicio de sesión / jugar como invitado*:
  - Jugadores invitados pueden unirse sin cuenta, pero no se guarda su historial ni puntuación.
- *Invitar amigos*:
  - Enviar invitación por correo o código.
  - También se puede invitar desde la lista de amigos.

### Interacción entre jugadores

- *Lista de amigos*:
  - Se pueden agregar o quitar amigos.
- *Jugadores expulsados*:
  - Posibilidad de expulsar jugadores que no cumplan con las reglas.
- *Lobby o sala de espera*:
  - Antes de empezar la partida, los jugadores esperan en una sala hasta que todos estén listos.
- *Chat colaborativo*:
  - Disponible tanto en la sala como durante la partida.
  - Opción extra: filtrar palabras ofensivas automáticamente.

### Funcionalidades del juego

- *Unirse a la partida*:
  - Botón que permite entrar a una partida activa.
- *Marcadores o tabla de ganadores*:
  - Mostrar el top 10 de los mejores jugadores.
- *Iniciar juego*:
  - Se podrá iniciar el juego cuando todos estén listos.
- *Personalización*:
  - Cambiar el diseño del tablero, colores, fichas y reglas opcionales (por ejemplo: número de fichas o fichas especiales)
  - *Registro de jugadores*
  - *Cambios de perfil*
  - *Cambiao de contraseña*

---



# Extras




## Personalisacion de la partida

- Estilos de *fichas personalizables* (formas: círculos, estrellas, cuadrados).
- Tableros con *temas visuales*: espacio, bosque, minimalista, neón.

- Sonidos personalizados
	- Agregar efectos de sonido: al mover una ficha, al ganar, al saltar una ficha, etc.
		-Permitir al usuario activar/desactivar los sonidos.
- Cada jugador elige el color de sus fichas y lado del tablero.

## Expansión 

- Una ventana que nos permita *cambiar el modo de juego* a diferentes versiones como por ejemplo:

	- Batlle royale
		- numero de jugadores entre 1-6
		- cada salto sobre una canica ajena a las nuestras elimina dicha canica
		- el ultimo jugador en tener una canica en juego, gana.
	- Long play
		- Mismas reglas que el original pero unicamente se permite un salto largo por turno

- Configuración del color de las fichas.




## Estadísticas del jugador 

Al ser un juego que implica estrategia consideramos importante el tener un ranking que nos permita no solo conocer nuestras estadísticas para poder compararnos con el resto de jugadores si no también el de los otros para conocer a quien nos enfrentamos tomando en cuenta datos mas que la cantidad de partidas jugadas y las victorias de estas. Por lo que proponemos los siguientes apartados.

- Tiempo de victoria.
- Cantidad de fichas saltadas.
- Cantidad promedio de movimientos para ganar


## Tutorial

Como hemos mencionado en puntos anteriores las damas chinas es un juego que requiere estrategia y consta de aunque pocas múltiples reglas que podrian ser difíciles de intuir si el usuario no tiene experiencia previa en este tipo de juegos por lo que vemos conveniente si el tiempo del proyecto lo permite agregar un tutorial interactivo que le permita al usuario familiarizarse con las reglas del juego.