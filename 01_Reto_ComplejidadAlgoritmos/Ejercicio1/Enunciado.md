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
- Las siguientes `C` líneas contienen un entero `N` → el número de casas (máx. `1E10`).  

### Salida
- Para cada caso, imprimir el número de la casa que cumple la condición o `"NO"` si no existe.  

---

### Recomendación
Cuando la salida requiera de muchas líneas, como en este caso que pueden ser hasta 20000, es más eficiente almacenar la respuesta en un string y luego hacer un solo print, que hacer 20000 print individuales.

---

### Ejemplo de entrada
```
3
8
5
9800
```

### Ejemplo de salida
```
6
NO
6930
```
