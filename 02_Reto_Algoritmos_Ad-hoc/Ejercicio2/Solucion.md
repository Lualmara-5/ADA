#  🌌 Problema: Día del Olimpo

---

## 📜 Enunciado resumido
Se nos da un conjunto de entre **2 y 5 planetas**, cada uno con el número de días que tarda en dar una vuelta alrededor del sol (su periodo de traslación).  

El objetivo es calcular cada cuántos días volverán a estar **todos alineados**, es decir, encontrar el número mínimo de días que es múltiplo común de todos esos periodos.

En otras palabras: hallar el **mínimo común múltiplo (MCM)** de la lista de periodos.

---

## 💡 Idea de la solución
- El problema se reduce a calcular el **MCM** de varios números (entre 2 y 5).  
- Recordemos la fórmula para dos números: <br>
  `mcm(a, b) = (a * b) // mcd(a, b)`
  donde `mcd` es el máximo común divisor (se obtiene con el algoritmo de Euclides).  
- Para más de dos números, aplicamos la fórmula de manera **iterativa**:
  - `mcm(x1, x2, x3) = mcm(mcm(x1, x2), x3)`  
  - Y así sucesivamente hasta combinar todos.  
- Python ofrece `math.gcd`, que implementa Euclides en `O(log M)`.  
- Como la lista es pequeña (máx. 5 planetas), basta recorrerla y aplicar la fórmula iterativamente.

---

## 💻 Código en Python
```python
import math

def mcm(a, b):
    return a * b // math.gcd(a, b)   # gcd = MCD = Máximo Común Divisor

casos = int(input())

for _ in range(casos):
    traslaciones = list(map(int, input().split()))
    resultado = traslaciones[0]
    for i in range(1, len(traslaciones)):
        resultado = mcm(resultado, traslaciones[i])
    print(resultado, "\n")
```
---

## ⚡ Complejidad

**Tiempo**: `O(k * log M)`
- `M` representa el **mayor valor de los números de entrada en el caso** *(M = max(a.b))*.
- `k` representa cuántos planetas tienes en la lista *(k ≤ 5)*. 
- Complejidad final: `O(log M)` por caso.

**Memoria**: `O(1)` -> (solo unas variables y la lista pequeña de 2–5 enteros)

---
