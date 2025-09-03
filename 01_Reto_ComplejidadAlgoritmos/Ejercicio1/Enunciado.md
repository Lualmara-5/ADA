# Ejercicio 1: Números de Casa 🏠

## Enunciado
Un programador vive en una calle con `N` casas numeradas consecutivamente desde `1` hasta `N`.  
Al salir de su casa, gira a la izquierda y suma todos los números de las casas en esa dirección.  
Al día siguiente hace lo mismo pero girando a la derecha.  

Se busca determinar si existe un número de casa tal que la suma de los números a la izquierda sea igual a la suma de los números a la derecha.  

- Si existe, se debe imprimir el número de esa casa.  
- Si no existe, se debe imprimir **NO**.  

**Ejemplo:**
- Para `N = 8`, la respuesta es la casa **6**.  
- Para `N = 5`, la respuesta es **NO**.  

### Entrada
- La primera línea contiene un número `C` → la cantidad de casos (máx. 20000).  
- Las siguientes `C` líneas contienen un entero `N` → el número de casas (máx. `1e10`).  

### Salida
- Para cada caso, imprimir el número de la casa que cumple la condición o `"NO"` si no existe.  

### Ejemplo de entrada
