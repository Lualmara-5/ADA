# 📘 Ejercicio 2: Número de Calle

## 📝 Enunciado
Una programadora vive en una ciudad donde todas las calles están numeradas consecutivamente desde `1` hasta `M`.  

Un día, al salir de su casa a trotar, giró a la izquierda y sumó los cuadrados de los números de las calles en esa dirección (sin incluir su propia calle).  

Al día siguiente hizo lo mismo pero hacia la derecha. Para su sorpresa, **la suma de la derecha resultó múltiplo de la de la izquierda**.   

Diseñemos entonces un algoritmo para determinar, dados el valor de (M) ((3 < M < 10000)) en cuántas calles (S) ((2 < S < M)) podría vivir la programadora para que se cumpla esa propiedad.

---

## 📊 Explicación con ejemplo
Si (M=8) y la programadora vive en la calle (3) tenemos que:

$4^2$ + $5^2$ + $6^2$ + $7^2$ + $8^2$ = 190

Es múltiplo de:

$1^2$ + $2^2$ = 5

Por otro lado, si (M = 42), hay dos calles (S) que cumplen la propiedad: (5) y (14).

---

### 📥 Entrada
- La entrada contiene varios casos de prueba, no más de `500`.  
- Cada caso corresponde a una línea con el valor de `M` (`3 < M < 10000`).  
- La entrada termina con un valor `0`, que **no corresponde a un caso**.  

### 📤 Salida
- Para cada caso de prueba, se debe imprimir una línea con la cantidad de calles que cumplen la propiedad.  

---

### ✅ Ejemplo
**Entrada:**
```
8
42
55
0
```

**Salida:**
```
1
2
0
```
