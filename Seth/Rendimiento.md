# Escenario de Rendimiento - Software de Gestión de Hoteles

**Fuente:**  
Un recepcionista del hotel

**Estímulo:**  
Solicita la disponibilidad de habitaciones para una fecha específica durante temporada alta

**Artefacto:**  
Módulo de reservas del sistema de gestión de la cadena hotelera

**Entorno:**  
El sistema está en operación normal, con múltiples usuarios concurrentes realizando consultas y reservas (pico de carga en temporada alta)

**Respuesta:**  
El sistema procesa la solicitud, accede a la base de datos centralizada de hoteles, recupera la información y muestra las habitaciones disponibles en pantalla

**Medida:**  
- La respuesta debe generarse en **menos de 2 segundos** para consultas de disponibilidad  
- Confirmación de reserva en **menos de 5 segundos**  
- Soporta al menos **500 usuarios concurrentes** sin degradación perceptible del servicio


**Importancia para el negocio (m)
**Dificultad tecnica (m)