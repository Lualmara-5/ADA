# 🔁 Problema: Números de Kaprekar

Este readme resuelve el problema "Números de Kaprekar", donde se busca determinar si un número entero positivo es Kaprekar, es decir, si su cuadrado puede descomponerse en dos partes cuya suma es igual al número original.

---

## 📜 Enunciado resumido
- Un número **Kaprekar** es un entero positivo mayor que 3.
- Al elevarlo al cuadrado, el resultado puede dividirse en dos partes (izquierda y derecha).
- La suma de esas dos partes debe ser igual al número original.
- La parte derecha *no puede ser **0**.

---

## 💡 Idea de la solución

1. Leer la cantidad de casos `C`.
2. Para cada número `n`:
- Ignorar si `n <= 3` (no se consideran Kaprekar).
- Calcular `sq = n²`.
- Convertir `sq` a cadena para poder dividirlo en distintas posiciones.
- Probar todas las formas de separar `sq` en dos partes:
  - `L = parte izquierda`
  - `R = parte derecha`
- Verificar si `R != 0` y `L + R == n`.
- Si alguna partición cumple → `KAP`.
- Si ninguna cumple → `NO`.

---

## 💻 Código en Python
```python
C = int(input().strip())

for _ in range(C):
    n = int(input().strip())

    if n <= 3:
        print("NO")
        continue

    sq = n * n 
    s = str(sq)
    encontrado = False

    for i in range(1, len(s)):
        left_part = s[:i]               
        right_part = s[i:]                

        L = int(left_part) if left_part else 0
        R = int(right_part) if right_part else 0

        if R != 0 and L + R == n:
            encontrado = True
            break

    print("KAP" if encontrado else "NO")
```

---

## ⚡ Complejidad
- Elevar al cuadrado: **O(1)**.
- Conversión a string: **O(d)**, siendo `d` la cantidad de dígitos de `n²` (máximo 12, porque `n < 1e6`).
- Revisión de cortes posibles: máximo `d-1` divisiones.
- Complejidad por caso: **O(d²)** (en la práctica muy pequeño).
- Complejidad total: **O(C · d²)**, con `C ≤ 20000` y `d ≤ 12`, perfectamente eficiente.

---
