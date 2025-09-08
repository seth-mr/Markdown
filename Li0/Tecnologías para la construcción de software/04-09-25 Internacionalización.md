SQLServer
Clases
Base -> Pensar en el juego de caracteres de la base
Repo

## Introducción
Es el proceso de diseñar software que se adapte a diferentes idiomas y regiones sin requerir cambios en su estructura.

Localización
Es el proceso de adaptar software a una región específica o idioma mediante la adición de componentes específicos y traducción de textos o mensajes.

*Globalización (g11n)* Generalmente comprende a la internacionalización y la configuración regional. Abarca al proceso de desarrollo orientado a la adopción del software en determinados mercados.

## ¿Por qué hacerlo?
- Adopción de modelos económicos globales
- El uso de software por mercados internacionales
- La adopción de dispositivos móviles permite utilizar más software.
- La adopción de prácticas o actividades a través de internet.
- Crecimiento de negocios basados en software.
- Construye una vez. vende muchas
- Facilidad de traducción

## ¿Qué implica técnicamente?
- Mensajes, elementos textuales, etiquetas no deben tener texto fijo
- Es necesario utilizar elementos externos para recuperarlos dinámicamente
- Agregar nuevos idiomas no necesita recompilación.
- Cuidar que elementos relacionados con la cultura como aspectos financieros y fechas respeten el formato de la región destino.



| ID                | Categoría | es-Mx   | en-Us  |
| ----------------- | --------- | ------- | ------ |
| galobalTextAccept | Global    | Aceptar | Accept |
