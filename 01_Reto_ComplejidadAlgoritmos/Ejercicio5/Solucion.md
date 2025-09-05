# 🔁 Problema: Números de Lychrel

Este readme resuelve el problema "Números de Lychrel", que consiste en aplicar el proceso de inversión y suma hasta llegar a un número capicúa, o detectar un posible número de Lychrel.

---

## 📜 Enunciado resumido
- Un número **capicúa** es aquel que se lee igual de izquierda a derecha y viceversa.
- El proceso consiste en que dado un número `n`:
    - Invertir sus cifras → `rev(n)`.
    - Sumarlo: `n = n + rev(n)`.
    - Repetir hasta obtener un capicúa.

- Si se obtiene un capicúa, la salida es el número de iteraciones necesarias.
- Si `n` ya es capicúa desde el inicio → `0`.
- Si durante el proceso el número llega a un valor `>= 1e10`, se imprime `"L"` para indicar que se sospecha que es un número de Lychrel

---

## 💡 Idea de la solución

1. Revisar si el número inicial ya es capicúa → `0`.
   
2. Si no, aplicar el proceso de inversión y suma.
   
3. Contar iteraciones hasta encontrar capicúa o hasta que el número ≥ `1e10`.
   
4. Imprimir el resultado correspondiente.

---

## 💻 Código en Python
```python
def es_capicua(n: int) -> bool:
    return str(n) == str(n)[::-1]

while True:
    n = int(input())
    if n == 0:
        break

    if es_capicua(n):
        print(0)
        continue

    iteraciones = 0
    limite = int(1e10) #10,000,000,000

    while n < limite:
        n = n + int(str(n)[::-1])
        iteraciones += 1
        if es_capicua(n):
            print(iteraciones)
            break
    else:
        print("L")
```

---

## ⚡ Complejidad

- Cada iteración invierte el número y compara cadenas → **O(d)**, siendo `d` la cantidad de dígitos.
- Máximo hasta que `n ≥ 1e10`, es decir, ≤ 10 dígitos → rápido en la práctica.
- Complejidad final: **O(I · d)**, donde `I` es el número de iteraciones realizadas.

---
