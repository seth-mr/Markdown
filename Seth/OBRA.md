

## Personajes
- **Moderador (Iván)**: Dirige la sesión, controla los tiempos y que se cumplan las reglas.  
- **Autor (LEO)**: Programador que desarrolló el sistema de inventario de películas.  
- **Revisor 1 (Gabriel - lógica y validación)**: Experto en detectar errores de funcionamiento y validaciones débiles.  
- **Revisor 2 (Seth - estilo y buenas prácticas)**: Enfocado en legibilidad, mantenibilidad y estructura.  
- **Registrador (Registrador)**: Documenta todos los defectos y acuerdos de la revisión.  

---

## Escenario
Una sala de juntas con laptops abiertas. En la pantalla se proyecta el código `inventario_peliculas.cpp`.

---

### Iván (Moderador)
“Bien, comenzamos la **revisión formal del sistema de inventario de películas**.  
Recordemos: el **autor explica**, los **revisores preguntan o señalan**, el **autor solo aclara, no discute**, y Leonardo documenta.  
Luis, adelante.”  

---

### LEO (Autor)
“El programa administra un catálogo de películas con estas funciones:  
- `cantidadANumero` y `precioANumero` convierten cadenas a enteros o flotantes.  
- `generarClave` construye una clave única para cada película.  
- Se almacenan hasta 50 productos en un arreglo estático.  
- Se pueden buscar por distribuidora, precio, o listar el catálogo completo.”  

---

### Gabriel (Revisor 1 - lógica)
(levanta la mano)  
“En `cantidadANumero`, si el usuario escribe `12abc`, el programa toma el número `12` como válido.  
Esto **no debería aceptarse**, porque el input está contaminado.”  

### LEO (Autor)
“Correcto, mi idea era extraer dígitos, pero veo que puede causar errores serios.”  

###  (Registrador)
- Defecto: Validación incorrecta de entradas, acepta valores no numéricos como válidos.  

---

### Gabriel
“También veo que `precioANumero` hace lo mismo: acepta caracteres mezclados.  
Además, si alguien mete `....45`, podría aceptar un precio inválido.”  

### Luis
“Sí, reconozco que no controlo los puntos decimales repetidos.”  

### Leonardo
- Defecto: Manejo inadecuado de decimales en `precioANumero`.  

---

### Gabriel
“En `generarClave`, haces esto: `numcad = '0' + numcad;`.  
Eso no concatena un cero, en realidad está sumando el valor ASCII del carácter.  
La clave podría quedar mal generada.”  

### Luis
“Sí, fue un error de concepto, quería rellenar con ceros a la izquierda.”  

### REGISRTADOR
- Defecto: Error en la generación de claves, implementación incorrecta de ceros a la izquierda.  

---

### Iván
“Muy bien. Pasemos al análisis de estilo y estructura.”  

---

### Seth (Revisor 2 - estilo)
“Luis, veo que tienes **mucho código repetido** en validaciones.  
¿No sería mejor crear una función genérica que valide tanto cantidades como precios con parámetros?”  

### LEO
“Sí, eso simplificaría bastante.”  

### REGISTRADOR
- Oportunidad de mejora: Reutilizar funciones de validación en lugar de duplicarlas.  

---

### Seth
“También usas un arreglo fijo de `producto peliculas[50]`.  
Eso limita el crecimiento. Si la empresa quiere manejar 500 películas, habría que reescribir código.  
Un `vector<producto>` resolvería eso fácilmente.”  

### LEO
“Entendido, tiene sentido.”  

### REGISTRADOR
- Oportunidad de mejora: Usar estructuras dinámicas como `vector` en lugar de arreglos estáticos.  

---

### Seth
“En cuanto a estilo:  
- Hay variables como `i`, `j`, `nP` que son poco claras.  
- Las funciones podrían dividirse en módulos más pequeños para ser más legibles.  
- La documentación dentro del código es mínima, cuesta entender la intención sin leer línea por línea.”  

### LEO
“Sí, acepto que no comenté lo suficiente.”  

### REGISTRADOR
- Defectos: Variables poco expresivas y falta de comentarios.  
- Oportunidad de mejora: Modularizar funciones largas.  

---

### Gabriel
“Un detalle más: cuando se llena el catálogo y se intenta registrar una película extra, el programa no maneja el desbordamiento.  
Se debería controlar e informar al usuario que no caben más registros.”  

### REGISTRADOR
- Defecto: Falta manejo de desbordamiento de catálogo.  

---

### Iván
“Perfecto, creo que hemos cubierto los puntos principales.  
Leonardo, ¿puedes leernos el acta de defectos y mejoras?”  

---

###  (Registrador)
“Claro, estos son los hallazgos de la revisión:  

1. **Defectos de validación**:  
   - `cantidadANumero` y `precioANumero` aceptan datos incorrectos.  
   - Manejo defectuoso de decimales múltiples.  

2. **Defecto de clave**:  
   - `generarClave` implementada con error en concatenación de ceros.  

3. **Defectos estructurales**:  
   - Código repetido en validaciones.  
   - Uso de arreglos estáticos limitados.  
   - Variables con nombres poco expresivas.  
   - Falta de comentarios.  
   - Sin control de desbordamiento del catálogo.  

4. **Oportunidades de mejora**:  
   - Uso de `vector` o estructuras dinámicas.  
   - Modularización de funciones.  
   - Mejor documentación en el código.”  

---

### Iván
“Excelente. Luis, tienes claro lo que debes corregir.  
Cerramos la revisión. Gracias a todos.”  

---


