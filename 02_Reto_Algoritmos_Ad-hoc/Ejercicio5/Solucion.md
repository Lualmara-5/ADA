#  📐 Problema: Secuencia NuNuDoN

---

## 📜 Enunciado resumido

---

## 💡 Idea de la solución

---

## 💻 Código en Python
```python
import math

def contar_divisores(x):
    divisores = 0
    raiz = int(math.isqrt(x))
    for i in range(1, raiz + 1):  
        if x % i == 0:
            divisores += 1
            if i != x // i:   
                divisores += 1
    return divisores

C = int(input())   
for _ in range(C):
    A, B = map(int, input().split())
    n = 1           
    contador = 0    

    while n <= B:  
        if A <= n <= B:
            contador += 1
        n = n + contar_divisores(n)

    print(contador)
```
---

## ⚡ Complejidad
- **Tiempo:** O(B * √B)
    - En el peor caso, supongamos que `n` crece lento (por ejemplo con números primos, que tienen pocos divisores) -> Entonces el ciclo puede dar hasta `O(B)` pasos.
- **Memoria:** O(1).

---
