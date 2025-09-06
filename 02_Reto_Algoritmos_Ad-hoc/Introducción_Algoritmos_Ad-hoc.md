# 📘 Introducción a Algoritmos Ad-hoc

En este módulo estudiaremos los **algoritmos ad-hoc**, junto con problemas clásicos relacionados con divisores, múltiplos, primos y búsqueda de elementos dominantes.

Los algoritmos ad-hoc se caracterizan por estar diseñados para resolver **un problema específico** de forma directa y eficiente, sin necesidad de recurrir a técnicas más generales o complejas como programación dinámica o divide & conquer.

---

## 📚 Temas a tratar

🔹1. [**Cantidad de divisores y Algoritmos ad-hoc**](#-ejemplo-divisores)

🔹2. [**Mínimo común múltiplo y Algoritmo de Euclides**](#-ejemplo-mínimo-común-múltiplo-de-dos-enteros)

🔹3. [**Números primos y Criba de Eratóstenes**](#-)

🔹4. [**Elemento dominante y Algoritmo Boyer-Moore**](#-)

🔹5. [**Algoritmo Z (búsqueda de patrones en cadenas)**](#-)

---

## 🛠️ Metodologías de solución de problemas computacionales
En la resolución de problemas de programación competitiva y análisis algorítmico existen diferentes metodologías o enfoques:
- **Búsqueda exhaustiva (Brute force):** probar todas las posibilidades.
- **Algoritmos voraces (Greedy):** elegir siempre la mejor opción local en cada paso.
- **Programación dinámica (Dynamic programming):** dividir un problema en subproblemas que se resuelven de forma óptima.
- **Divide y vencerás (Divide & Conquer):** dividir el problema en partes más pequeñas, resolverlas y combinar las soluciones.
- **Algoritmos ad-hoc:** soluciones específicas y directas, diseñadas a medida del problema.

---

## 📊 Ejemplo: divisores
Dado un valor entero positivo `N`, mostrar todos sus divisores diferentes de `1` y `N`.

### 📝 Solución 1 (pseudocódigo)
```bash
read N
for i = 2 to N-1:
    if N % i == 0:
        print i
```

📌 Si `N = 100`, la salida sería:
```bash
2, 4, 5, 10, 20, 25, 50
```

### ⚡ Complejidad
El bucle recorre `N-2` valores, por lo que el número de operaciones es: `f(N) = N - 1`

La complejidad es: `O(N)`

---

### 📝 Solución 2 (pseudocódigo)
```bash
read N
for i = 2 to N//2:
if N % i = 0:
print i
```

📌 Si `N = 100`, la salida sería:
```bash
2, 4, 5, 10, 20, 25, 50
```

### 🚀 ¿Qué cambia respecto a la Solución 1?
En la primera ibas de `2` hasta `N-1`.
Pero piensa:

👉 ¿tiene sentido dividir `N` por un número mayor que `N/2`?

Ejemplo:
- Si `N = 100`, ¿sirve probar `i = 60`? <br>
No, porque `100 / 60 ≈ 1.66`, nunca va a dar un divisor exacto. <br>
El máximo divisor distinto de N siempre está en `N/2`.

Por eso ahora el bucle llega solo hasta `N//2`.

### ⚡ Complejidad
Ahora el bucle va hasta `N/2` en lugar de `N`.
- En Solución 1: ≈ **N operaciones**
- En Solución 2: ≈ **N/2 operaciones**

Matemáticamente: `f(N)= (N/2) −1 +1 =(N/2)`

La complejidad es: `O(N)` (sigue siendo O(N), pero **más eficiente en la práctica** porque hace la mitad de comparaciones.)

---

### 📝 Solución 3 (pseudocódigo)
```bash
read N
for i = 2 to sqrt(N):
    if N % i == 0:
        if i ≠ sqrt(N):
            print(i, N/i)
        else:
            print(i)   
```

📌 Si `N = 100`, la salida sería:
```bash
2, 50, 4, 25, 5, 20, 10
```

### 💡 Cambio clave
En lugar de iterar hasta `N`, el bucle va solo hasta √N.

¿Por qué? Porque los divisores vienen en pares complementarios:
- Si `i` divide a `N`, entonces también `N/i` es divisor.
- Basta con encontrar los menores o iguales a √N, y el complemento lo sacamos con `N/i`.

Ejemplo con `N = 100`:
- Recorres hasta √100 = 10.
- Cuando `i = 2` → imprimes `2` y `100/2 = 50`.
- Cuando `i = 4` → imprimes `4` y `25`.
- Cuando `i = 5` → imprimes `5` y `20`.
- Cuando `i = 10` (justo la raíz) → solo imprimes una vez el 10, no dos.

👉 Así obtienes los divisores con menos iteraciones y sin perder ninguno.

### ⚡ Complejidad
- El bucle ya no recorre `N` ni `N/2`.
- Solo va hasta **√N**.
- Entonces la complejidad es: `O(√N)`

Lo que es muchísimo mejor que `O(N)` cuando `N` es grande. 🚀

### 📊 Resumen de las 3 soluciones:

1. For hasta `N-1` → **O(N)**

2. For hasta `N/2` → **O(N)** (mitad de operaciones, pero misma clase)

3. For hasta `√N` → **O(√N)** ✅ la mejor

Matemáticamente: `f(N)= (N/2) −1 +1 =(N/2)`

La complejidad es: `O(N)` (sigue siendo O(N), pero **más eficiente en la práctica** porque hace la mitad de comparaciones.)

---

## 📊 Ejemplo: Mínimo común múltiplo de dos enteros
Dados dos enteros positivos A y B, cuál es el mínimo valor que es múltiplo de ambos

### 📝 Solución 1 (pseudocódigo)
```bash
read A, B
mayor = max(A,B)
menor = min(A,B)

for M = mayor to mayor*menor step mayor:
    if M % menor == 0:
        print M
        break
```

### 🔎 ¿Qué hace?
- Arranca en el mayor de los dos números.
- Va sumando de a "mayor" (step mayor).
- Se detiene cuando encuentra un múltiplo de "menor".
- Ese será el mínimo común múltiplo.

Ejemplo:
- A = 6, B = 4
- mayor = 6, menor = 4
- Probar: 6, 12, 18, 24 → el 12 funciona, porque 12%4 = 0.
- Resultado: mcm = 12 ✅

### ⚡ Complejidad
El ciclo no recorre hasta infinito, sino que como máximo llega hasta: `mayor x menor` <br> *(porque siempre se garantiza que ahí ya estará un múltiplo común)*.

Pero no da cada paso de 1, sino de **"mayor"**.
Es decir, el número de pasos que el bucle hace es: `(mayor x menor) / mayor = menor `

👉 Eso significa que en el peor caso, el ciclo hace menor iteraciones.
👉 La complejidad es: `O(min(A,B)`

---

### 📝 Solución 2 (pseudocódigo + Algoritmo de Euclides)
El algoritmo de Euclides se basa en:
1. Al dividir `M` entre `N`, ambos números enteros, se obtiene un cociente `Q` más un residuo `R`
2. El máximo común divisor de `M` y `N` es igual que el de `N` y `R`
3. A*B = MinimoComunMultiplo(A, B) * MaximoComunDivisor(A, B)

```bash
read A, B
M, N = A, B

while N ≠ 0:
    M, N = N, M%N

MaxCD = M
MinCM= A*B/MaxCD
```

### 📊 Ejemplo:
A es 1043, B es 987 → M = 1043, N = 987

- Iteración 1: M = 987, N = 56 -> *(1043 = 987 × 1 + 56)*
- Iteración 2: M = 56, N = 35
- Iteración 3: M = 35, N = 21
- Iteración 4: M = 21, N = 14
- Iteración 5: M = 14, N = 7
- Iteración 6: M = 7, N = 0 (versus 141 iteraciones de la solución 1)
  
**MinCD** = 1043 * 987 / 7 = **147063**

*Nota:* En Python existen los métodos gcd() y lcm() en la librería math*

### ⚡ Complejidad
- La complejidad del algoritmo es O(log(max(A,B))

---

## 📊 Ejemplo: 3
## 📊 Ejemplo: 4
## 📊 Ejemplo: 5
