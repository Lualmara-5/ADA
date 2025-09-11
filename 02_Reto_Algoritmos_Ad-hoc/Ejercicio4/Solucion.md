# ⏰ Problema: Fabricación de relojes

---

## 📜 Enunciado resumido
Una fábrica de relojes necesita colocar ciertos símbolos en cada reloj (I, V, X, o cualquier otro sistema similar).

Los símbolos se fabrican usando un **molde**, que puede repetirse varias veces, pero debe estar diseñado de forma que **no sobre ni falte ningún símbolo** al armar un reloj.

Dados los requerimientos de símbolos de cada tipo, se pide calcular el **tamaño mínimo del molde** (número total de símbolos que debe contener) para que, repitiéndolo varias veces, se pueda construir un reloj sin desperdicio.

---

## 💡 Idea de la solución
- El molde debe ser proporcional a las cantidades requeridas.
- Para minimizar su tamaño, buscamos la **proporción irreducible** entre los tres números de símbolos.
- Esa proporción se obtiene dividiendo cada cantidad entre el **máximo común divisor (MCD)** de todas ellas.
- Finalmente, el tamaño del molde es la suma de esas cantidades reducidas.

Ejemplo:
Si se necesitan `20 I, 4 V, 4 X`, el `MCD = 4`.
- Molde mínimo → `(20/4) + (4/4) + (4/4) = 5 + 1 + 1 = 7`.

---

## 💻 Código en Python
```python
import math

N = int(input())
for _ in range(N):
    a, b, c = map(int, input().split())
    g = math.gcd(a, math.gcd(b, c))
    molde = (a // g) + (b // g) + (c // g)
    print(molde)
```
---

## ⚡ Complejidad
- **Tiempo:** O(N * log(min(a,b,c))) por el cálculo del MCD (Algoritmo de Euclides).
- **Memoria:** O(1).

---
