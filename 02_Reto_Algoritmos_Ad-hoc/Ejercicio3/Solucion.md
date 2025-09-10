#  🌌 Problema: Teorema de los Números Primos

---

## 📜 Enunciado resumido
Dado un número entero `n`, se pide calcular la diferencia entre:
- `P(n)`: la cantidad de números primos menores o iguales a `n`.
- `n / ln(n)`: la aproximación teórica de la cantidad de primos según el Teorema de los Números Primos.

Es decir, hay que calcular: `e = P(n) - ( n / ln(n) )` para varios casos de prueba.

---

## 💡 Idea de la solución
1. Para obtener **P(n)** (la cantidad de primos menores o iguales a `n`), una forma eficiente es usar el **algoritmo de la Criba de Eratóstenes**.
   
2. La parte analítica se calcula con la fórmula:  
   ```python
   import math
   aprox = n / math.log(n)
   ```

3. Finalmente, el error se obtiene como:
   ```bash
   error = P[n] - aprox
   ```
   
4. No olvides **redondear al entero más cercano** usando `round(error)`.

---

## 💻 Código en Python (Solución 1)
```python
def criba_eratostenes(n):

  is_prime = [True] * (n + 1)
  is_prime[0] = is_prime[1] = False

  for i in range (2, int(n**0.5) + 1):
    if is_prime[i]:
      for j in range (i * i, n + 1, i):
        is_prime[j] = False

  return sum(is_prime)

import math

C = int(input())

for _ in range (C):

  n = int(input())
  P = criba_eratostenes(n)
  aprox = n / math.log(n)
  e = P - aprox
  print(round(e))
```

## 📊 Ejemplo (Trayectoria `n=30`):

- Inicial: `is_prime` = `[False, False, True, True, True, True, ..., True]` (índices 0..30).
- `i = 2`: marcamos `4, 6, 8, 10, ..., 30` como `False`.
- `i = 3`: marcamos `9, 12, 15, 18, ..., 30` como `False` (muchos ya estaban, pero 9 y 15 se marcan ahora).
- `i = 4`: saltado porque `is_prime[4]` es `False`.
- `i = 5`: marcamos `25` (y 30 ya estaba).
- **Resultado final**: los `True` corresponden a `[2,3,5,7,11,13,17,19,23,29]` → `sum(is_prime) = 10`.

---

## ⚡ Complejidad
- Tiempo: `O(N*log(log(N))` 
- Memoria: `O(N)` → se necesita un arreglo de tamaño `N` para guardar los booleanos.

---

## 💻 Código en Python (Solución 2)
```python
import math

MAXN = 100000

is_prime = [True] * (MAXN + 1)
is_prime[0] = is_prime[1] = False

for i in range(2, int(MAXN**0.5) + 1):
    if is_prime[i]:
        for j in range(i * i, MAXN + 1, i):
            is_prime[j] = False

P = [0] * (MAXN + 1)
for i in range(1, MAXN + 1):
    P[i] = P[i-1] + (1 if is_prime[i] else 0)

C = int(input())
for _ in range(C):
    n = int(input())
    aprox = n / math.log(n)
    e = P[n] - aprox
    print(round(e))
```
---

## 📊 Ejemplo con MAXN = 10
Supongamos que después de la criba is_prime quedó así:
```bash
Número : Primo?
0 -> False
1 -> False
2 -> True
3 -> True
4 -> False
5 -> True
6 -> False
7 -> True
8 -> False
9 -> False
10 -> False
```

Ahora calculamos P:

- `P[0] = 0` (no hay primos hasta el 0)
- `P[1] = P[0] + 0 = 0`
- `P[2] = P[1] + 1 = 1` (porque 2 es primo)
- `P[3] = P[2] + 1 = 2` (porque 3 es primo)
- `P[4] = P[3] + 0 = 2` (4 no es primo)
- `P[5] = P[4] + 1 = 3` (5 es primo)
- `P[6] = P[5] + 0 = 3`
- `P[7] = P[6] + 1 = 4` (7 es primo)
- `P[8] = P[7] + 0 = 4`
- `P[9] = P[8] + 0 = 4`
- `P[10] = P[9] + 0 = 4`

Resultado final:
```bash
P = [0,0,1,2,2,3,3,4,4,4,4]
```
👉 Interpretación:
- `P[5] = 3` significa que **hay 3 primos** ≤ 5 (2,3,5).
- `P[10] = 4` significa que **hay 4 primos** ≤ 10 (2,3,5,7).

## ⚡ Complejidad
- Tiempo: `O(MAXN*log(log(MAXN))`
- Cada consulta se responde en O(1).
- Memoria: `O(MAXN)` → se necesita un arreglo de tamaño `MAXN` para guardar los booleanos.

---

## 📊 Resumen de las 2 soluciones:
- **Solución 1 (sin MAXN)**:
    - Para cada `n` vuelves a calcular la criba desde cero.
    - Si pones un caso con `C = 10000` y cada `n` grande, estás haciendo miles de veces la criba → demasiado lento → **TLE (Time Limit Exceeded)**.

- **Solución 2 (con MAXN)**:
    - Solo haces la criba **una vez** hasta 100000.
    - Cada consulta se resuelve en **O(1)** con `P[n]`.
    - Aunque haya 10000 consultas, es rapidísimo
