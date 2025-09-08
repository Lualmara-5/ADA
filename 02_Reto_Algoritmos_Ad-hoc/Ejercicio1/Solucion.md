#  🪖 Problema: Organización de batallones

Este readme resuelve el problema "Organización de batallones", que consiste en determinar de cuántas formas un ejército de tamaño `E` puede organizarse en batallones de **igual tamaño**.

En otras palabras: hallar la cantidad de divisores de `E`.

---

## 📜 Enunciado resumido
Dado un ejército de `E` soldados, Saurón quiere repartirlos en batallones de igual tamaño.
Se pide calcular cuántas distribuciones posibles existen, sabiendo que:

- El tamaño mínimo de un batallón es 1 soldado.
- `2 ≤ E ≤ 500.000`.
- Se darán `N` casos de prueba (máx. 100).

**Ejemplo:**

- Para `E = 200000`, hay 42 formas de dividirlo en batallones.
- Para `E = 25`, hay 3 formas.

---

## 💡 Idea de la solución

El problema se reduce a contar divisores de un número entero `E`.

- Cada divisor `d` representa una manera de repartir el ejército en batallones de tamaño `d` soldados.
- Para optimizar, basta revisar divisores hasta `√E`, porque:
  - Si `i` divide a `E`, entonces también lo divide `E/i`.
  - Así contamos dos divisores al mismo tiempo (`i` y `E//i`).
  - Con cuidado de no duplicar cuando `i = √E` (cuadrados perfectos).

---

## 💻 Código en Python
```python
import math
N = int(input())

for _ in range (N):
  E  = int(input())
  divisores = 0

  raiz = math.isqrt(E)

  for i in range (1, raiz + 1):
    if E % i == 0:
      divisores += 1
      if i != E // i:
        divisores += 1

  print(divisores)
```
---

## ⚡ Complejidad
- **Tiempo:** O(√E) -> (porque el ciclo va solo hasta la raíz de E)
- **Memoria:** O(1) -> (solo usamos contadores y variables simples)

---
